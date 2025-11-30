---
title: Boss Limbs Update Script
category: entities
---

# Boss Limbs Update Script

This Lua script defines the behavior and attack patterns for the "Boss Limbs" entity in Noita. It manages the boss's movement states, attack phases, and visual animations.

## Core Logic States

The script defines several states for the boss's AI, synchronized with C++ logic.

*   `MoveAroundNest = 0`: The boss moves around its nest area.
*   `FollowPlayer = 1`: The boss actively pursues the player.
*   `Escape = 2`: The boss attempts to flee from the player.
*   `DontMove = 3`: The boss remains stationary.

## Key Functions and Behaviors

### Attack Phases

The boss cycles through various attack phases, each with a distinct set of actions.

*   `phase0()`: Initializes with `FollowPlayer` state, waits, and then randomly chooses another phase.
*   `phase1()`: Enters `DontMove` state, exposes a weak spot, performs `circleshot` attacks, keeps the weak spot exposed for a duration, then hides it and chooses a random phase.
*   `phase2()`: Enters `FollowPlayer` state, spawns minions, waits, and then chooses a random phase.
*   `phase3()`: Enters `FollowPlayer` state, initiates a chase sequence (`prepare_chase`, `chase_start`), waits, stops the chase, and then transitions to `phase1`.
*   `phase4()`: Enters `DontMove` state, exposes a weak spot, performs `homingshot` attacks, keeps the weak spot exposed, then hides it and transitions to `phase0`.

### Attack Patterns

*   `circleshot()`: Fires a spread of projectiles in a circular pattern around the boss.
*   `homingshot()`: Fires a projectile that tracks the player.
*   `spawn_minion()`: Spawns "slimeshooter_boss_limbs" minions, with a limit on the number of active minions.

### Movement and Animation Control

*   `prepare_chase()`: Sets up the animation for a chase sequence.
*   `chase_start()`: Increases the boss's `force_coeff` for faster movement and sets `eat_probability` for its `CellEaterComponent`.
*   `chase_stop()`: Resets `force_coeff` and `eat_probability` to their original values.
*   `expose_weak_spot()`: Animates the boss to open, hides details, enables weak spot hitboxes, and waits.
*   `hide_weak_spot()`: Animates the boss to close, disables weak spot hitboxes, shows details, and waits.
*   `set_main_animation(current_name, next_name)`: Controls the main sprite's animation.
*   `animate_random_detail()`: Randomly animates one of the boss's detail sprites.
*   `set_details_hidden(is_hidden)`: Controls the visibility and animation of the boss's details.
*   `animate_sprite(sprite, current_name, next_name)`: Helper function to set sprite animations.

### State Management

*   `set_logic_state(state)`: Updates the boss's AI state via the `LimbBossComponent`.
*   `choose_random_phase()`: Selects a random attack phase for the boss to execute.

### Death Sequence

*   `check_death()`: Monitors the boss's HP. If HP drops to 0 or below, it triggers a death sequence:
    *   Disables the "limb_attacker" child entity.
    *   Plays death animations and particle effects.
    *   Sets `kill_now` to true to despawn the entity.
*   `boss_wait(frames)`: A utility function that checks for death before and after a wait period.

## Initialization

The script initializes the boss with:
*   Weak spot hitboxes disabled.
*   Idle animation set.
*   Details visible.

## Main Loop

An `async_loop` continuously calls the current `state()` function if the boss is alive, or waits if it's dead.

```lua
-- enum for changing C++ logic state. keep this in sync with the values in limbboss_system.cpp
MoveAroundNest = 0
FollowPlayer   = 1
Escape         = 2
DontMove       = 3

local details_hidden = false
local is_dead        = false

-- gather some data we're gonna reuse --------------
local herd_id = get_herd_id( GetUpdatedEntityID() )
local force_coeff_orig = component_get_value_float(  GetUpdatedEntityID(), "PhysicsAIComponent", "force_coeff", 10.0 )

-- animate eyes and skull randomly -----------------
async_loop(function()
	wait(120)
	if details_hidden == false then
		animate_random_detail()
	end
end)

-- do various attack patterns -----------------
function phase0()
	-- init
	set_logic_state( FollowPlayer )
	-- timeline
	boss_wait(5 * 60)
	choose_random_phase()
end

function phase1()
	-- init
	set_logic_state( DontMove )
	-- open and shoot
	expose_weak_spot()
	circleshot()
	boss_wait(50)
	circleshot()
	boss_wait(50)
	circleshot()
	-- keep the weak spot temporarily exposed
	boss_wait(3 * 80)
	-- close
	hide_weak_spot()
	boss_wait(10)
	choose_random_phase()
end

function phase2()
	-- init
	set_logic_state( FollowPlayer )
	-- timeline
	spawn_minion()
	boss_wait(30)
	spawn_minion()
	boss_wait(100)
	choose_random_phase()
end

function phase3()
	-- init
	set_logic_state( FollowPlayer )
	-- timeline
	prepare_chase()
	chase_start()
	boss_wait(1 * 80)
	chase_stop()
	state = phase1
end

function phase4()
	-- init
	set_logic_state( DontMove )
	-- open and shoot
	expose_weak_spot()
	homingshot()
	boss_wait(40)
	homingshot()
	boss_wait(2 * 60)
	-- close
	hide_weak_spot()
	boss_wait(10)
	state = phase0
end

function choose_random_phase()
	local r = math.random(0,4)
	if     r == 0 then state = phase0
	elseif r == 1 then state = phase1
	elseif r == 2 then state = phase2
	elseif r == 3 then state = phase3
	else               state = phase4
	end
end

-- helpers -----------------
function circleshot()
	set_main_animation( "attack_ranged", "opened" )
	boss_wait(15)

	local this         = GetUpdatedEntityID()
	local pos_x, pos_y = EntityGetTransform( this )

	local angle  = 0
	local amount = 16
	local space  = math.floor(360 / amount)
	local speed  = 130
	
	for i=1,amount do
		local vel_x = math.cos( math.rad(angle) ) * speed
		local vel_y = math.sin( math.rad(angle) ) * speed
		angle = angle + space

		local orb = shoot_projectile( this, "data/entities/animals/boss_limbs/orb_boss_limbs.xml", pos_x, pos_y, vel_x, vel_y )
	end
end

function homingshot()
	set_main_animation( "attack_ranged", "opened" )
	boss_wait(15)

	local this         = GetUpdatedEntityID()
	local pos_x, pos_y = EntityGetTransform( this )

	local vel_x = 0
	local vel_y = -30

	shoot_projectile( this, "data/entities/projectiles/orb_pink_big.xml", pos_x, pos_y, vel_x, vel_y )
end

function spawn_minion()
	-- check that we only have less than N minions
	local existing_minion_count = 0
	local existing_minions = EntityGetWithTag( "slimeshooter_boss_limbs" )
	if ( #existing_minions > 0 ) then
		existing_minion_count = #existing_minions
	end

	if existing_minion_count >= 2 then
		return
	end

	-- spawn
	local x, y = EntityGetTransform( GetUpdatedEntityID() )
	
	SetRandomSeed( GameGetFrameNum(), x + y )
	
	local slime = EntityLoad( "data/entities/animals/boss_limbs/slimeshooter_boss_limbs.xml", x, y )
	edit_component( slime, "VelocityComponent", function(comp,vars)
		local vel_x = Random(-90,90)
		local vel_y = Random(-150,25)
		ComponentSetValueVector2( comp, "mVelocity", vel_x, vel_y )
	end)

	edit_component( slime, "GenomeDataComponent", function(comp,vars)
		vars.herd_id = herd_id
	end)
end

function get_idle_animation_name()
	return "stand"
end

function prepare_chase()
	set_main_animation( "charge", get_idle_animation_name() )
	boss_wait(40)
end

function chase_start()
	local physics_ai = EntityGetFirstComponent( GetUpdatedEntityID(), "PhysicsAIComponent" )
	ComponentSetValue( physics_ai, "force_coeff", tostring( force_coeff_orig * 5.0 ) )
	
	local celleater = EntityGetFirstComponent( GetUpdatedEntityID(), "CellEaterComponent" )
	ComponentSetValue( celleater, "eat_probability", tostring(100.0) )
end

function chase_stop()
	local physics_ai = EntityGetFirstComponent( GetUpdatedEntityID(), "PhysicsAIComponent" )
	ComponentSetValue( physics_ai, "force_coeff", tostring( force_coeff_orig ) )
	
	local celleater = EntityGetFirstComponent( GetUpdatedEntityID(), "CellEaterComponent" )
	ComponentSetValue( celleater, "eat_probability", tostring(0.0) )
end
	
function expose_weak_spot()
	set_main_animation( "open", "opened" )
	set_details_hidden( true )
	boss_wait(10)
	set_hitboxes_weak( true )
	boss_wait(20)
end

function hide_weak_spot()
	set_main_animation( "close", get_idle_animation_name() )
	boss_wait(10)
	set_hitboxes_weak( false )
	boss_wait(30)
	set_details_hidden( false )
end

function set_hitboxes_weak( weak_spot_exposed )
	EntitySetComponentsWithTagEnabled( GetUpdatedEntityID(), "hitbox_weak_spot", weak_spot_exposed )
	EntitySetComponentsWithTagEnabled( GetUpdatedEntityID(), "hitbox_default",   weak_spot_exposed == false )
end

function set_main_animation( current_name, next_name )
	local sprite = EntityGetFirstComponent( GetUpdatedEntityID(), "SpriteComponent" )
	if ( sprite ~= nil ) then
		animate_sprite( sprite, current_name, next_name )
	end
end

function animate_random_detail()
	local which = math.random(1, 3)
	for_comps( "SpriteComponent", function(i,sprite)
		if i == which + 1 then
			animate_sprite( sprite, "animate", "stand" )
		end
	end)
end

function set_details_hidden( is_hidden )
	if is_hidden then
		set_detail_animation( "invisible" )
	else
		set_detail_animation( "stand" )
	end
	details_hidden = is_hidden
end

function set_detail_animation( current_name )
	for_comps( "SpriteComponent", function(i,sprite)
		if i > 1 then
			ComponentSetValue( sprite, "rect_animation", current_name )
		end
	end)
end

function animate_sprite( sprite, current_name, next_name )
	ComponentSetValue( sprite, "rect_animation",      current_name )
	ComponentSetValue( sprite, "next_rect_animation", next_name )
end

function set_logic_state( state )
	local comp = EntityGetFirstComponent( GetUpdatedEntityID(), "LimbBossComponent" )
	if( comp ~= nil ) then
		ComponentSetValue( comp, "state", state )
	end
end

function check_death()
	local comp = EntityGetFirstComponent( GetUpdatedEntityID(), "DamageModelComponent" )
	if( comp ~= nil ) then
		local hp = ComponentGetValueFloat( comp, "hp" )
		if ( hp <= 0.0 ) then
			-- disable the attack limb
			local children = EntityGetAllChildren( GetUpdatedEntityID() )
			for i,child in ipairs( children ) do
				if EntityGetName( child ) == "limb_attacker" then
					EntityKill( child )
				end
			end
			
			SetRandomSeed( GameGetFrameNum(), GameGetFrameNum() )

			-- run death sequence
			set_hitboxes_weak( false )
			set_details_hidden( true )
			set_logic_state( DontMove )
			set_main_animation( "death1", "death2" )

			local rand = function() return Random( -10, 10 ) end

			for i = 1,40 do
				local x,y = EntityGetTransform( GetUpdatedEntityID() )
			    GameScreenshake( i * 1, x, y )
				GameCreateParticle( "slime_green",            x + rand(), y + rand(), 10, i * 5.5, i * 5.5, true, false )
				if i > 20 then
					GameCreateParticle( "gunpowder_unstable", x + rand(), y + rand(), 3,  40.0,    40.0,    true, false )
				end
				wait( 3 )
			end

			-- kill
			comp = EntityGetFirstComponent( GetUpdatedEntityID(), "DamageModelComponent" )
			if( comp ~= nil ) then
				ComponentSetValue( comp, "kill_now", "1" )
			end

			is_dead = true

			return
		end
	end
end

function boss_wait( frames )
	check_death()
	wait( frames )
	check_death()
end

-- init --------------------------------------------
set_hitboxes_weak( false )
set_main_animation( get_idle_animation_name(), get_idle_animation_name() )
set_details_hidden( false )

-- run phase state machine -----------------
state = phase0

async_loop(function()
	-- alive
	if is_dead then
		wait(60 * 10)
	else
		state()
	end
end)
```