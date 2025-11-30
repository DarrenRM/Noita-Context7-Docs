---
title: Noita Modding Utilities
source: https://noita.wiki.gg/wiki/Modding:_Utilities
category: modding-wiki
---

# Modding: Utilities

This documentation page provides a collection of useful Lua scripts and techniques developed by the Noita modding community. These utilities can be directly incorporated into your mods to streamline common tasks, enhance debugging, and implement complex behaviors, saving you significant development time and effort.

## Obtaining Player Entity ID

This function retrieves the entity ID of the player, allowing you to access and manipulate player-specific data and components.

```lua
-- simple utility function to return the player entity
function getPlayerEntity()
	local players = EntityGetWithTag("player_unit")
	if #players == 0 then return end

	return players[1]
end
```

## Easier Entity Debugging

The following functions provide enhanced tools for inspecting and understanding entity data, which is crucial for debugging modded content.

```lua
function str(var)
  if type(var) == 'table' then
    local s = '{ '
    for k,v in pairs(var) do
      if type(k) ~= 'number' then k = '"'..k..'"' end
      s = s .. '['..k..'] = ' .. str(v) .. ','
    end
    return s .. '} '
  end
  return tostring(var)
end

function debug_entity(e)
    local parent = EntityGetParent(e)
    local children = EntityGetAllChildren(e)
    local comps = EntityGetAllComponents(e)

    print("--- ENTITY DATA ---")
    print("Parent: ["..parent.."] " .. (EntityGetName(parent) or "nil"))

    print(" Entity: ["..str(e).."] " .. (EntityGetName(e) or "nil"))
    print("  Tags: " .. (EntityGetTags(e) or "nil"))
    if (comps ~= nil) then
      for _, comp in ipairs(comps) do
          print("  Comp: ["..comp.."] " .. (ComponentGetTypeName(comp) or "nil"))
      end
    end

    if children == nil then return end

    for _, child in ipairs(children) do
        local comps = EntityGetAllComponents(child)
        print("  Child: ["..child.."] " .. EntityGetName(child))
        for _, comp in ipairs(comps) do
            print("   Comp: ["..comp.."] " .. (ComponentGetTypeName(comp) or "nil"))
        end
    end
    print("--- END ENTITY DATA ---")
end
```

To use these functions, simply call `debug_entity(entity)` with the entity ID you wish to inspect.

## Adding Custom Names in Translations

This script, placed in your mod's `init.lua`, allows you to add custom names for entities that will appear in the game's translations.

You should use a CSV file with the exact same headers as `data/translations/common.csv`.

```lua
local translations = ModTextFileGetContent("data/translations/common.csv")
local new_translations = ModTextFileGetContent("mods/modid/files/translations.csv")
translations = translations .. "\n" .. new_translations .. "\n"
translations = translations:gsub("\r", ""):gsub("\n\n+", "\n")
ModTextFileSetContent("data/translations/common.csv", translations)
```

**Note:** Custom translations applied in `init.lua` will not be reflected in the mod's settings UI from the main menu.

## Adding New Genomes (Compatible with Other Mods)

The `add_new_genome` function enables you to append new genome entries to `data/genome_relations.csv`, ensuring compatibility with other mods that modify this file. Use this function in your `init.lua`.

```lua
function split_string(inputstr, sep)
  sep = sep or "%s"
  local t= {}
  for str in string.gmatch(inputstr, "([^"..sep.."]+)") do
    table.insert(t, str)
  end
  return t
end

local content = ModTextFileGetContent("data/genome_relations.csv")

--The function works like this: genome_name is the name of your new genome/faction,
--default_relation_ab is the relation with all the horizontal genomes which relations weren't specified in the table,
--default_relation_ba is the relation with all the vertical genomes which relations weren't specified in the table,
--self relation is the genome's relation with itself,
--relations is a table which directly specifies the value of the genome relation with.

function add_new_genome(content, genome_name, default_relation_ab, default_relation_ba, self_relation, relations)
  local lines = split_string(content, "\r\n")
  local output = ""
  local genome_order = {}
  for i, line in ipairs(lines) do
    if i == 1 then
      output = output .. line .. "," .. genome_name .. "\r\n"
    else
      local herd = line:match("([%w_-]+),")
      output = output .. line .. ","..(relations[herd] or default_relation_ba).."\r\n"
      table.insert(genome_order, herd)
    end
  end

  local line = genome_name
  for i, v in ipairs(genome_order) do
    line = line .. "," .. (relations[v] or default_relation_ab)
  end
  output = output .. line .. "," .. self_relation

  return output
end

-- Example usage: (This sets all genome relations of this genome to 100, unless indicated so, in this case, I want 100 with everything, except the player and -1)
content = add_new_genome(content, "genome1", 100, 100, 100, {
  player = 0,
  ["-1"] = 0
})
--Here I want 0 genome relations with everything, except for 100 with itself
content = add_new_genome(content, "genome2", 0, 0, 100, {})

ModTextFileSetContent("data/genome_relations.csv", content)
```

## Adding a New Tag to an Existing Entity File

This function allows you to add a tag to an existing entity without needing to overwrite its entire XML definition.

```lua
function add_tags()

	local xml2lua = dofile("mods/new_enemies/files/xml2lua_library/xml2lua.lua")
	local xml_content = ModTextFileGetContent("data/entities/props/existing_entity.xml")
	local handler = xml2lua.parse(xml_content)
	if handler.root.Entity._attr.tags then
	  handler.root.Entity._attr.tags = handler.root.Entity._attr.tags .. ",your_tag_name"
	else
	  handler.root.Entity._attr.tags = "your_tag_name"
	end
	local xml_output = xml2lua.toXml(handler.root, "Entity", 0)
	ModTextFileSetContent("data/entities/props/existing_entity.xml", xml_output)

end

add_tags_seamine()
```

## Rotating Entity Based on Terrain Topology

This script makes an entity rotate to align with the surrounding terrain.

```lua
function approx_rolling_average(avg, new_sample, n)
  avg = avg - avg / n;
  avg = avg + new_sample / n;
  return avg
end

local old_average = GetValueNumber("average_rotation", 0)

function get_direction( x1, y1, x2, y2 )
  return math.atan2( ( y2 - y1 ), ( x2 - x1 ) )
end

local entity_id = GetUpdatedEntityID()
local x, y = EntityGetTransform(entity_id)
local found_normal, normal_x, normal_y, approximate_distance_from_surface = GetSurfaceNormal(x, y, 60, 16)
local dir = get_direction(0, 0, normal_x, normal_y)
local degree_shift = math.rad(-90) + dir -- 90 degree rotation to properly orient the entity
local new_average = approx_rolling_average(old_average, degree_shift, 5) -- if the number is higher than 5 the turning speed would be smoother and slower, if less it would be more instantaneous
SetValueNumber("average_rotation", new_average)

if found_normal then
 EntitySetTransform(entity_id, x, y, new_average)
end
```

Attach this script to your entity's XML using a `LuaComponent`:

```xml
    <LuaComponent
		_enabled="1"
		script_source_file="mods/yourmod/files/the_script_above.lua"
		execute_every_n_frame="1">
   </LuaComponent>
```

## Shooting Projectiles from an Entity Towards the Player

This script, by Evaisa, enables entities to shoot projectiles directly at the player.

```lua
dofile( "data/scripts/lib/utilities.lua" )

function rotate_degrees(x, y, degrees)
	return rotate_radians(x, y, math.rad(degrees))
end

function rotate_radians(x, y, radians)
	local ca = math.cos(radians)
	local sa = math.sin(radians)
	local out_x = ca * x - sa * y
	local out_y = sa * x + ca * y
	return out_x, out_y
end

function shoot_at_entity(self_entity, target_entity, general_offset, x_offset, y_offset, speed, projectile, maxdistance, max_player_distance, rotation_offset)
	local rad_offset = 0
	if(rotation_offset ~= nil)then
		rad_offset = rotation_offset
	end
	local x, y = EntityGetTransform(self_entity)

	if(target_entity ~= nil)then
		local entityX, entityY = EntityGetTransform( target_entity )

		local headingX = entityX - (x + x_offset)
		local headingY = (entityY-5) - (y + y_offset)

		local len = math.sqrt((headingX*headingX) + (headingY*headingY))

		local directionX = headingX / len
		local directionY = headingY / len

		local didHit, hitX, hitY = RaytraceSurfaces( x, y, entityX, entityY )

		local headingHitX = entityX - hitX
		local headingHitY = entityY - hitY

		local hitDistance = math.sqrt((headingHitX*headingHitX) + (headingHitY*headingHitY))

		local pos_x, pos_y, currentRotation = EntityGetTransform( self_entity )

		if(directionX < 0)then
			EntitySetTransform(self_entity,pos_x,pos_y,currentRotation,-1,1)
		else
			EntitySetTransform(self_entity,pos_x,pos_y,currentRotation,1,1)
		end

		if(len < max_player_distance)then
			if(hitDistance < maxdistance)then

				directionX, directionY = rotate_degrees(directionX, directionY, rad_offset)


				local ourProjectile = shoot_projectile( self_entity, projectile, x + (directionX * general_offset) + x_offset, y + (directionY * general_offset) + y_offset, directionX * speed, directionY * speed )
				edit_component( ourProjectile, "ProjectileComponent", function(comp,vars)
					vars.mWhoShot       = self_entity
					vars.mShooterHerdId = "player"
				end)
			end
		end
	end
end
```

To use this function, call it with the following parameters:

`shoot_at_entity([Attacker Entity], [Target Entity], [Projectile offset towards target], [Projectile Start X offset], [Projectile Start Y offset], [Projectile speed], [Projectile xml], [Distance to sense through walls], [Distance to see target])`

Then, attach a Lua component to the entity's XML that utilizes this script and executes periodically:

```xml
<LuaComponent
  script_source_file="mods/yourmod/files/previous_script.lua"
  execute_every_n_frame="100"
  >
</LuaComponent>
```

## Attaching Entities to Verlet Chains

This script allows you to attach custom entities to existing verlet chains.

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity = GetUpdatedEntityID()

local _, _, day, hour, minute, second = GameGetDateAndTimeLocal()
SetRandomSeed(day + hour + second, minute + second + entity)

local verlet_data = {point_count = 0, positions = {}}

local x, y = EntityGetTransform(entity)

local verlet_entities = {}
local verlet_files = {}
local empty_percentage = 0

component_read( EntityGetFirstComponent( entity, "VerletPhysicsComponent" ), { positions = {} }, function(comp)

    verlet_data.point_count = (#comp.positions / 2)

    for i = 1, verlet_data.point_count, 4 do
        local point = {x = 0, y = 0}
        point.x, point.y = comp.positions[i], comp.positions[i + 1]
        table.insert(verlet_data.positions, point)
    end
end)

function set_verlet_position(verlet, x, y)
    component_readwrite( EntityGetFirstComponent( verlet, "VerletPhysicsComponent" ), { positions = {} }, function(comp)
        comp.positions[1] = x
        comp.positions[2] = y
    end)
end

function delimiter_split(input, delimiter)
    local word_table = {}
    for word in string.gmatch(input, '([^'..delimiter..']+)') do
        table.insert(word_table, word)
    end
    return word_table
end

function tablelength(T)
    local count = 0
    for _ in pairs(T) do count = count + 1 end
    return count
end

local holder = nil

local variable_storage = EntityGetComponent(entity, "VariableStorageComponent")

for k, v in pairs(variable_storage)do
    local name = ComponentGetValue2(v, "name")

    if(name == "verlet_entity")then
        table.insert(verlet_entities, tonumber(ComponentGetValue2(v, "value_string")))
    elseif(name == "verlet_files")then
        verlet_files = delimiter_split(ComponentGetValue2(v, "value_string"), ',')
    elseif(name == "holder")then
        holder = tonumber(ComponentGetValue2(v, "value_string"))
    end
end

for k, position in pairs(verlet_data.positions)do
    if(verlet_entities[1] ~= nil)then
        if(verlet_entities[k] ~= 0)then
            if(EntityGetIsAlive(verlet_entities[k]))then
                EntitySetTransform(verlet_entities[k], position.x, position.y)
                set_verlet_position(verlet_entities[k], position.x, position.y)
            end
        end
    else
        if(0 == empty_percentage)then

			-- for k, position in pairs(verlet_data.positions)do
			    -- if k % 2 == 0 then
					local verlet_file = verlet_files[Random(1, #verlet_files)]
					local verlet = EntityLoad(verlet_file, x, y)
					EntityAddChild(entity, verlet)
					if(verlet ~= nil)then

						EntityAddComponent(entity, "VariableStorageComponent", {
							name="verlet_entity",
							value_string=tostring(verlet),
						})
					   -- GamePrint("holder = "..holder)
						if(holder ~= 0)then
							EntityAddComponent(holder, "VariableStorageComponent", {
								name="verlet_entity",
								value_string=tostring(verlet),
							})
						end

					end
				-- end
			-- end
        else
            EntityAddComponent(entity, "VariableStorageComponent", {
                name="verlet_entity",
                value_string="0",
            })
        end
    end
end
```

Add this to your verlet chain entity's XML:

```xml
    <VariableStorageComponent
        name="verlet_files"
        value_string="mods/yourmod/files/entity_you_want_to_attach_to_verlet.xml"
    ></VariableStorageComponent>

    <LuaComponent
	_enabled="1"
	script_source_file="mods/yourmod/files/the_lua_script_above.lua"
	execute_on_added="1"
	execute_every_n_frame="0">
    </LuaComponent>
```

This will attach one entity to each verlet chain segment. Be aware that this can be performance-intensive.

## Rotating Physics Object Towards Player

This script makes a physics object rotate to face the player.

```lua
dofile_once("data/scripts/lib/utilities.lua")

local this_entity = GetUpdatedEntityID()

local x, y, r = EntityGetTransform(this_entity)

local variable_storage = EntityGetComponent(this_entity, "VariableStorageComponent")

local aim_direction = {x = 0, y = 0}

local players = EntityGetWithTag("player_unit")

if #players > 0 then

	local player_x, player_y = EntityGetTransform(players[1])

	local direction_x, direction_y = player_x - x, player_y - y

	local len = math.sqrt((direction_x*direction_x) + (direction_y*direction_y))

	aim_direction.x, aim_direction.y = direction_x / len, direction_y / len

	local phys_body = EntityGetFirstComponent(this_entity, "PhysicsBodyComponent")

	local ang_vel = PhysicsGetComponentAngularVelocity( this_entity, phys_body )

	function angle_rad(direction)
		return math.atan2(direction.y,direction.x)
	end

	function get_torque(current_angle, target_angle, speed)
		-- Make angle go from 0 to 2pi
		if target_angle < 0 then
		  target_angle = target_angle + math.pi * 2
		end
		if current_angle < 0 then
		  current_angle = current_angle + math.pi * 2
		end

		local dist_up = math.abs(target_angle - current_angle)
		local dist_down = math.abs((current_angle + math.pi * 2) - target_angle)

		if current_angle > target_angle then
		  dist_up = math.abs((target_angle + math.pi * 2) - current_angle)
		  dist_down = math.abs(current_angle - target_angle)
		end

		local dir
		if math.abs(dist_up) < math.abs(dist_down) then
		  dir = 1
		else
		  dir = -1
		end
		local dist_smallest = dist_up
		if dist_down < dist_up then
		  dist_smallest = dist_down
		end

		local new_angle = speed * dir

		return new_angle
	end

	PhysicsApplyTorque( this_entity, -ang_vel )

	PhysicsApplyTorque( this_entity, get_torque(r, angle_rad(aim_direction), 5) )

end
```

Attach this script to your entity's XML using a Lua component:

```xml
    <LuaComponent
		_enabled="1"
		script_source_file="mods/yourmod/files/the_script_above.lua"
		execute_every_n_frame="1">
   </LuaComponent>
```

For this to work correctly, ensure that any `PhysicsAIComponent` on the entity has its torque values set to 0:

```xml
<PhysicsAIComponent
	torque_balancing_coeff="0"
	torque_coeff="0"
	torque_max="0" >
</PhysicsAIComponent>
```

## Checking if Inside Wall

This function helps prevent entities from spawning inside solid walls.

```lua
function is_inside_wall(x, y, radius)
  for i=1,8 do
    local slice = math.pi * 2 / 8 * i
    local did_hit, hit_x, hit_y = RaytraceSurfacesAndLiquiform(x, y, x + math.cos(slice) * radius, y + math.sin(slice) * radius)
    if did_hit then
      return true
    end
  end
  return false
end

if not is_inside_wall(x, y, 32) then
  -- Whatever you want to do!
end
```

## Player Movement Checking

These functions provide flags to determine the player's current movement state.

```lua
-- returns "right" if the player is moving right, "left" if the player is  moving left, or an empty string if neither
function getPlayerHorizontalMovement()
	local vel_x, vel_y = getPlayerVelocities()
	local horizontal_movement = ""
	if(vel_x > 10) then
		horizontal_movement = "right"
	end
	if(vel_x < -10) then
		horizontal_movement = "left"
	end
	return horizontal_movement
end

-- returns "down" if the player is falling, "up" if the player is going up, or an empty string if neither
function getPlayerVerticalMovement()
	local vel_x, vel_y = getPlayerVelocities()
	local vertical_movement = ""
	if(vel_y > 0 and vel_y ~= 60) then
		vertical_movement = "down"
	end
	if(vel_y < 0) then
		vertical_movement = "up"
	end
	return vertical_movement
end

-- returns true if the player is moving, or false otherwise
function isPlayerMoving()
    local flag = false
    local x, y = EntityGetTransform( getPlayerEntity() )

    local movement_threshold = 0.1
    if old_position and (math.abs(x - old_position.x) > movement_threshold or math.abs(y - old_position.y) > movement_threshold) then
        flag = true
    end
    old_position = {x=x, y=y};

    return flag
end

-- returns true if the player is standing on solid ground, or false if in the air
function isPlayerStanding()
    local vel_x, vel_y = getPlayerVelocities()
    if(vel_y == 60) then -- default gravity value when the player is standing on something solid
        return true
    else
        return false
    end
end

-- obtains x and y velocities from the player
function getPlayerVelocities()
    local cdc_id = EntityGetFirstComponentIncludingDisabled(getPlayerEntity(), "CharacterDataComponent")
    local velocity_x, velocity_y = ComponentGetValue2(cdc_id, "mVelocity")
    return velocity_x, velocity_y
end
```

## Obtaining and Setting Gold Amount

These functions allow you to manipulate the player's gold.

```lua
-- function to add or subtract gold from player
-- amount can be either negative or positive
function addPlayerGold(amount)

	local player = getPlayerEntity()

	local wallet = EntityGetFirstComponent(player, "WalletComponent")
	local money = ComponentGetValueInt(wallet, "money")
	local player_money = money + amount

	edit_component(player, "WalletComponent", function(comp,vars)
		vars.money = player_money
	end)
end

-- function to get player gold
function getPlayerGold()

	local player = getPlayerEntity()

	local wallet = EntityGetFirstComponent(player, "WalletComponent")
	local money = ComponentGetValueInt(wallet, "money")

	return money
end
```

## Internal Variable Manipulation

These functions are used to access and modify internal variables stored within an entity's `VariableStorageComponent`. Both `get` and `set` functions assume the variable already exists.

```lua
-- function to obtain a value from an internal variable contained in a variable storage component
-- entity_id is the id of the entity whose internal variables will be accessed
-- variable_name is the name of the internal variable to be accesses
-- variable_type is type indicator of the internal variable, which can be value_string, value_int or value_float
function getInternalVariableValue(entity_id, variable_name, variable_type)
	local value = nil
	local components = EntityGetComponent( entity_id, "VariableStorageComponent" )
	if ( components ~= nil ) then
		for key,comp_id in pairs(components) do
			local var_name = ComponentGetValue2( comp_id, "name" )
			if(var_name == variable_name) then
				value = ComponentGetValue2(comp_id, variable_type)
			end
		end
	end
	return value
end

-- function to set a value of an internal variable contained in a variable storage component of an entity with entity_id with name variable_name and type variable_type
-- entity_id is the id of the entity whose internal variables will be accessed
-- variable_name is the name of the internal variable to be accesses
-- variable_type is type indicator of the internal variable, which can be value_string, value_int or value_float
function setInternalVariableValue(entity_id, variable_name, variable_type, new_value)

	local components = EntityGetComponent( entity_id, "VariableStorageComponent" )
	if ( components ~= nil ) then
		for key,comp_id in pairs(components) do
			local var_name = ComponentGetValue2( comp_id, "name" )
			if( var_name == variable_name) then
				ComponentSetValue2( comp_id, variable_type, new_value )
			end
		end
	end
end

-- function to add new internal variables to an entity
-- entity_id is the id of the entity that will receive a new internal variable
-- variable_type is the type of variable being added, can be value_int, value_string or value_float
-- initial_value is the starting value of the variable being added, if none, must be provided as, e.g., 0, "", or 0.0
function addNewInternalVariable(entity_id, variable_name, variable_type, initial_value)
	if(variable_type == "value_int") then
		EntityAddComponent2(entity_id, "VariableStorageComponent", {
			name=variable_name,
			value_int=initial_value
		})
	elseif(variable_type == "value_string") then
		EntityAddComponent2(entity_id, "VariableStorageComponent", {
			name=variable_name,
			value_string=initial_value
		})
	elseif(variable_type == "value_float") then
		EntityAddComponent2(entity_id, "VariableStorageComponent", {
			name=variable_name,
			value_float=initial_value
		})
	elseif(variable_type == "value_bool") then
		EntityAddComponent2(entity_id, "VariableStorageComponent", {
			name=variable_name,
			value_bool=initial_value
		})
	end
end
```

## Player Health Manipulation

These functions allow you to get and modify the player's health.

```lua
-- function to return player health
-- health values are treated internally as floats, so if the player has 5 health, the internal value will be 0.008
function getPlayerHealth()
	local damagemodels = EntityGetComponent( getPlayerEntity(), "DamageModelComponent" )
	local health = 0
	if( damagemodels ~= nil ) then
		for i,v in ipairs(damagemodels) do

			health = tonumber( ComponentGetValue( v, "hp" ) )
			--GamePrint(health)
			break
		end
	end
	return health
end

-- function to return player max health
function getPlayerMaxHealth()
	local damagemodels = EntityGetComponent( getPlayerEntity(), "DamageModelComponent" )
	local maxHealth = 0
	if( damagemodels ~= nil ) then
		for i,v in ipairs(damagemodels) do

			maxHealth = tonumber( ComponentGetValue( v, "max_hp" ) )

			break
		end
	end
	return maxHealth
end

-- function to add to player health
-- amount is how much is player health to be added to, may be positive or negative
-- amount must be provided as an integer
-- overheal_flag tells the function if amount can update maximum health when amount added goes beyond it
function addPlayerHealth(amount, overheal_flag)

	local damagemodels = EntityGetComponent( getPlayerEntity(), "DamageModelComponent" )

	if( damagemodels ~= nil ) then
		for i,v in ipairs(damagemodels) do

			currentHealth = tonumber( ComponentGetValue( v, "hp" ) )
			currentMaxHealth = tonumber( ComponentGetValue( v, "max_hp") )

			local trueAmount = amount * 0.04 -- how health scaling works when shown by UI
			local updatedHealth = currentHealth + trueAmount
			local updatedMaxHealth = 0

			local updatedHealth = currentHealth + trueAmount
			if(updatedHealth > currentMaxHealth and overheal_flag) then -- overhealing, if new health goes beyond max health, max health is updated
				updatedMaxHealth = updatedHealth
				ComponentSetValue( v, "max_hp", updatedMaxHealth)
				ComponentSetValue( v, "hp", updatedHealth)
			else
				if(updatedHealth <= 0) then
					updatedHealth = 0.04
				end
				ComponentSetValue( v, "hp", updatedHealth) -- sets health to 1 when updatedHealth is zero or below
			end

			break
		end
	end
end

-- function to directly set a value to player health
-- newHealth is the new health the player is going to have
-- newHealth must be provided as a float value
function setPlayerHealth(newHealth)
	local damagemodels = EntityGetComponent( getPlayerEntity(), "DamageModelComponent" )

	if( damagemodels ~= nil ) then
		for i,v in ipairs(damagemodels) do
			ComponentSetValue( v, "hp", newHealth)
		end
	end
end
```

## Get and Set Basic Damage Multipliers

These functions are useful for obtaining and modifying the damage multipliers of any creature with a valid entity ID.

```lua
-- get all basic damage multipliers from entity with entity_id
function getBasicDamageMultipliers(entity_id)
	local dmc_id = EntityGetFirstComponentIncludingDisabled(entity_id, "DamageModelComponent")

	local ice = ComponentObjectGetValue2( dmc_id, "damage_multipliers", "ice" )
	local fire = ComponentObjectGetValue2( dmc_id, "damage_multipliers", "fire" )
	local drill = ComponentObjectGetValue2( dmc_id, "damage_multipliers", "drill" )
	local slice = ComponentObjectGetValue2( dmc_id, "damage_multipliers", "slice" )
	local melee = ComponentObjectGetValue2( dmc_id, "damage_multipliers", "melee" )
	local projectile = ComponentObjectGetValue2( dmc_id, "damage_multipliers", "projectile" )
	local radioactive = ComponentObjectGetValue2( dmc_id, "damage_multipliers", "radioactive" )
	local explosion = ComponentObjectGetValue2( dmc_id, "damage_multipliers", "explosion" )
	local electricity = ComponentObjectGetValue2( dmc_id, "damage_multipliers", "electricity" )

	return ice, fire, drill, slice, melee, projectile, radioactive, explosion, electricity
end

-- gets the value for a damage multiplier of an entity with entity_id
-- multiplier_name must be either ice, fire, drill, slice, melee, projectile, radioactive, explosion or electricity
function getBasicDamageMultiplier(entity_id, multiplier_name)
	local dmc_id = EntityGetFirstComponentIncludingDisabled(entity_id, "DamageModelComponent")
	local multiplier = ComponentObjectGetValue2( dmc_id, "damage_multipliers", multiplier_name )
	return multiplier
end

-- sets a new value for a damage multiplier of an entity with entity_id
-- multiplier_name must be either ice, fire, drill, slice, melee, projectile, radioactive, explosion or electricity
function setBasicDamageMultiplier(entity_id, multiplier_name, new_multiplier)
	local dmc_id = EntityGetFirstComponentIncludingDisabled(entity_id, "DamageModelComponent")

	ComponentObjectSetValue2( dmc_id, "damage_multipliers", multiplier_name, new_multiplier )
end
```

## Verlet Carrion Legs Script - by Horscht

This script gives your entity verlet tentacles that attach to walls, inspired by the game Carrion.

```lua
dofile_once("data/scripts/lib/utilities.lua")

------- CONFIG------
local num_limbs = 5
local angle_spread = 220
local cast_length = 200
local move_speed = 5
local resting_length = 20
--------------------

local entity_id = GetUpdatedEntityID()
local x, y = EntityGetTransform(entity_id)
local last_x = GetValueNumber("last_x", x)
local last_y = GetValueNumber("last_y", y)
local vx, vy = x - last_x, y - last_y
local last_direction = GetValueNumber("last_direction", 0)
local direction = math.atan2(vy, vx)
if math.abs(vx) + math.abs(vy) > 0.1 then
  direction = rot_lerp(direction, last_direction, 0.05)
else
  direction = last_direction
end
SetValueNumber("last_direction", direction)
SetValueNumber("last_x", x)
SetValueNumber("last_y", y)
SetRandomSeed(x + entity_id, y)

if not GetValueBool("initialized", false) then
  SetValueBool("initialized", true)
  for i=1, num_limbs do
    local ent = EntityLoad("data/entities/verlet_chains/vines/verlet_vine_pixelscene.xml")
    EntityAddComponent2(ent, "VerletWorldJointComponent")
    EntitySetName(ent, "tentacle_limb")
    SetValueNumber("jiggle_speed_"..tostring(i), Randomf(1, 3))
    EntityAddChild(entity_id, ent)
  end
end

local i = 0
for _, child in ipairs(EntityGetAllChildren(entity_id)) do
  if EntityGetName(child) ~= "tentacle_limb" then goto continue end
  i = i + 1
  -- The limb's current position
  local x2, y2 = GetValueNumber("x_"..tostring(i), x), GetValueNumber("y_"..tostring(i), y)
  -- The position it's currently moving towards
  local target_x, target_y = GetValueNumber("target_x_"..tostring(i), x), GetValueNumber("target_y_"..tostring(i), y)
  local anchor_found = GetValueBool("anchor_found_"..tostring(i), false)
  local cast_direction_x, cast_direction_y = vec_rotate(math.cos(direction), math.sin(direction), math.rad(-angle_spread/2 + (i-1) * angle_spread / (num_limbs-1)))
  local move_x, move_y = vec_normalize(target_x - x2, target_y - y2)
  x2 = x2 + move_x * move_speed
  y2 = y2 + move_y * move_speed
  if math.abs(x2 - target_x) < 5 then
    x2 = target_x
  end
  if math.abs(y2 - target_y) < 5 then
    y2 = target_y
  end

  if not anchor_found then
    SetValueNumber("target_x_"..tostring(i), x + cast_direction_x * resting_length)
    SetValueNumber("target_y_"..tostring(i), y + cast_direction_y * resting_length)
  end

  -- Only do the raytracing stuff every x frames because it's probably expensive
  if GameGetFrameNum() % 20 == 0 then
    -- Check if there's still a pixel to hold on to
    local pixel_found = GetSurfaceNormal(target_x, target_y, 2, 16)
    if not pixel_found then
      anchor_found = false
    end
    -- target_hit checks if there's an obstacle between the main body and target
    local target_hit, target_hit_x, target_hit_y = RaytraceSurfaces(x, y, target_x - cast_direction_x * 2, target_y - cast_direction_y * 2)
    local distance_to_target = get_distance(x, y, target_x, target_y)

    -- Check if anchor is still in sight and range
    if not anchor_found or target_hit or (anchor_found and distance_to_target > cast_length) then
      -- Lost sight of anchor or anchor too far away, look for new anchor
      local hit, hit_x, hit_y = RaytraceSurfaces(x, y, x + cast_direction_x * cast_length, y + cast_direction_y * cast_length)
      if hit then
        -- Found new anchor, set target to it
        SetValueNumber("target_x_"..tostring(i), hit_x)
        SetValueNumber("target_y_"..tostring(i), hit_y)
        SetValueBool("anchor_found_"..tostring(i), true)
      else
        SetValueBool("anchor_found_"..tostring(i), false)
      end
    end
  end

  SetValueNumber("x_"..tostring(i), x2)
  SetValueNumber("y_"..tostring(i), y2)

  local verlet_component = EntityGetFirstComponentIncludingDisabled(child, "VerletPhysicsComponent")
  local verlet_world_joint_component = EntityGetFirstComponentIncludingDisabled(child, "VerletWorldJointComponent")
  local positions = ComponentGetValue2(verlet_component, "positions")
  local add_wave = anchor_found and 0 or 3
  local jiggle_speed = GetValueNumber("jiggle_speed_"..tostring(i), 1)
  positions[27] = x2 + math.cos(GameGetFrameNum() * 0.02 + jiggle_speed) * add_wave
  positions[28] = y2 + math.sin(GameGetFrameNum() * 0.05 + jiggle_speed) * add_wave
  ComponentSetValue2(verlet_component, "positions", positions)
  -- world_position is the origin of the verlet
  ComponentSetValue2(verlet_world_joint_component, "world_position", x, y)
  ::continue::
end
```

Place this script in a Lua component on the entity that should have tentacles:

```xml
   <LuaComponent
        script_source_file="mods/your_mod/files/scripts/this_script.lua"
        execute_on_added="1"
        execute_every_n_frame="1"
        >
    </LuaComponent>
```

## Finding the Polymorphed Player

This function returns the entity ID of the polymorphed player. If no player is polymorphed, it returns `nil`.

```lua
function get_polyd_player()
    return EntityGetWithTag("polymorphed_player")[1]
end
```

## Modifying XML Files

For modifying XML files, it is highly recommended to use Zatherz' XML parser library, available at [https://github.com/NathanSnail/luanxml](https://github.com/NathanSnail/luanxml).

You can retrieve the content of an XML file using `ModTextFileGetContent`, parse it with the XML parser, make your modifications (refer to the GitHub page for documentation), and then save it back using `ModTextFileSetContent`. To convert the NXML object back into a string for saving, use `tostring()`. Alternatively, `nxml.edit_file` can be used for direct file editing with automatic handling of modifications and parsing.

Keep in mind that `ModTextFileGet/SetContent` functions are only available in `init.lua` and are removed after `OnMagicNumbersAndWorldSeedInitialized` has executed. Therefore, these modifications must be performed before this point, typically at the global level in `init.lua`.

Here's an example of how to change the durability of the EDR to 5 in the `data/materials.xml` file:

```lua
local nxml = dofile_once("nxml.lua")
local content = ModTextFileGetContent("data/materials.xml")
local xml = nxml.parse(content)
for element in xml:each_child() do
  if element.attr.name == "rock_hard_border" then
    element.attr.durability = 5
  end
end
ModTextFileSetContent("data/materials.xml", tostring(xml))
```

Here's how to add a biome to `data/biome/_biomes_all.xml`:

```lua
local nxml = dofile_once("nxml.lua")
local content = ModTextFileGetContent("data/biome/_biomes_all.xml")
local xml = nxml.parse(content)
xml:add_child(nxml.parse([[\
<Biome\
  biome_filename="mods/yourmod/files/biomes/your_biome.xml"\
  height_index="0"\
  color="ff123456">\
</Biome>\
]]))
ModTextFileSetContent("data/biome/_biomes_all.xml", tostring(xml))
```

## Constraining an Entity to a Set of Coordinates - Thatrius

This script pulls an affected entity back if it moves too far from a target point. It works with physics objects.

```lua
function constrain(entity, x2, y2, max_dist)
    local chardatacomp = EntityGetFirstComponent(entity, "CharacterDataComponent")
    local projcomp = EntityGetFirstComponent(entity, "VelocityComponent")
    local physcomp = EntityGetFirstComponent(entity, "PhysicsBodyComponent") or EntityGetFirstComponent(entity1, "PhysicsBody2Component") or EntityGetFirstComponent(entity1, "SimplePhysicsComponent")
    local vel_x, vel_y = ComponentGetValue2(chardatacomp, "mVelocity")
    local proj_vel_x, proj_vel_y = ComponentGetValue2(projcomp, "mVelocity")
    local x1, y1 = EntityGetTransform(entity)
    if (not x1) or (not x2) then return nil end

    local dist = math.sqrt(((x2-x1)^2) + ((y2-y1)^2))
    local target_x = x2 + (((x1-x2)/dist)*max_dist)
    local target_y = y2 + (((y1-y2)/dist)*max_dist)
    local target_vel_x = target_x - x1
    local target_vel_y = target_y - y1

    if dist > max_dist then
        if physcomp or not proj_vel_x then
            PhysicsApplyForce(entity, target_vel_x*100, target_vel_y*100)
        end
        if vel_x then
            vel_y = vel_y - 60
            local target_mag = math.sqrt((target_vel_x^2) + (target_vel_y^2))
            local mag = math.sqrt((vel_x^2) + (vel_y^2)) / 40
            local force_x = ((target_vel_x/target_mag)*mag)
            local force_y = ((target_vel_y/target_mag)*mag)

            vel_x = ((vel_x + force_x)*1.025) + (target_vel_x*dist*0.8)
            vel_y = ((vel_y + force_y)*1.025) + (target_vel_y*dist*0.8)
            EntitySetTransform(entity, target_x, target_y)
            if ComponentGetValue2(chardatacomp, "is_on_ground") == false then vel_x = vel_x*1.16 end
            ComponentSetValue2(chardatacomp, "mVelocity", vel_x, vel_y+60)
        elseif proj_vel_x then
            ComponentSetValue2(projcomp, "mVelocity", proj_vel_x+(target_vel_x*100), proj_vel_y+(target_vel_y*100))
            EntitySetTransform(entity, target_x, target_y)
        end
    end
end
```

To constrain two entities to each other, run the `constrain` function on each, using the other's coordinates:

```lua
x1, y1 = EntityGetTransform(entity1)
x2, y2 = EntityGetTransform(entity2)
constrain(entity1, x2, y2, 50)
constrain(entity2, x1, y1, 50)
```

## Inverse Kinematics Script (Works with More Than 2 Limb Parts)

This script, by Thatrius, implements Inverse Kinematics for entities with multiple limb segments.

```lua
---------------------------------------------------------------------------------
--Define Functions
---------------------------------------------------------------------------------
function distance(x1,y1,x2,y2)
    return math.sqrt((x1 - x2)^2 + (y1 - y2)^2)
end

function approx_rolling_average(avg, target, n)
    avg = avg - avg / n;
    avg = avg + target / n;
    return avg
end
local smoothness_factor = 6

---------------------------------------------------------------------------------
--General Setup
---------------------------------------------------------------------------------
local entity = GetUpdatedEntityID()
local ex, ey = EntityGetTransform(entity)

local parent = EntityGetParent(entity)
local vel_x, vel_y = GameGetVelocityCompVelocity(parent)
local vel_mag = math.sqrt((vel_x)^2 + (vel_y)^2)
local futurex, futurey = ex+(vel_x*60), ey+(vel_y*60)

local lengthcomp = EntityGetFirstComponent(entity, "VariableStorageComponent", "length")
local target = {GetValueNumber("targ_x", ex), GetValueNumber("targ_y", ey)}
local length = ComponentGetValue2(lengthcomp, "value_int")
local time = GetValueNumber("time", 0)

---------------------------------------------------------------------------------
--Inverse Kinematics
---------------------------------------------------------------------------------
--organize the segments and joints into neat little tables:
local legments = {} --"leg" + "segments"... haha funny word combo do you get
local joints = {}
local knees = {}
for i, child in ipairs(EntityGetAllChildren(entity)) do
    if not EntityHasTag(child, "knee") then
        local x, y = EntityGetTransform(child)
        if x == 0 then x = 1 end --safeguards against stupid "nan"s by making sure the code can never divide 0/0. Lost a piece of my soul in the frustration brought about by trying to track down a bug cause by this. Why does 0/0 have to equal "nan" in lua anyways and not just 0 or something, it serves no purpose except to create frustration, this is utterly retarted
        if y == 0 then y = 1 end
        table.insert(legments, child)
        if i == 1 then table.insert(joints, {ex, ey}) else table.insert(joints, {x, y}) end
    else
        table.insert(knees, child)
    end
end
table.insert(joints, target)

--First pass, starting at end of chain:
for i = #joints, 1, -1 do
    if i == #joints then
        --move joint directly to the target coords:
        joints[i] = target
    elseif i ~= 1 then
        --move joint within range of the previous one iterated:
        local jx, jy = joints[i][1], joints[i][2]
        local jx2, jy2 = joints[i+1][1], joints[i+1][2]
        if jx == jx2 or jy == jy2 then jx, jx = jx+1, jy+1 end --more nan-avoiding bullcrap
        local joint_dist = distance(jx, jy, jx2, jy2)
        local jx = jx2 + (((jx-jx2) / joint_dist) * length)
        local jy = jy2 + (((jy-jy2) / joint_dist) * length)
        joints[i] = {jx, jy}
    end
end

--Second pass, starting at beginning of chain:
for i, joint in ipairs(joints) do
    if i ~= 1 then
        --move joint within range of the previous one iterated:
        local jx, jy = joints[i][1], joints[i][2]
        local jx2, jy2 = joints[i-1][1], joints[i-1][2]
        if jx == jx2 or jy == jy2 then jx, jx = jx+1, jy+1 end
        local joint_dist = distance(jx, jy, jx2, jy2)
        local jx = jx2 + (((jx-jx2) / joint_dist) * length)
        local jy = jy2 + (((jy-jy2) / joint_dist) * length)
        joints[i] = {jx, jy}
    end
end

--Arrange all the legments to connect in between the joints:
for i, legment in ipairs(legments) do
    local jx, jy = math.floor(joints[i][1]), math.floor(joints[i][2])
    local jx2, jy2 = joints[i+1][1], joints[i+1][2]
    if jx == jx2 or jy == jy2 then jx, jx = jx+1, jy+1 end
    local vec_x, vec_y = jx2-jx, jy2-jy
    local targ_rot = math.atan2(vec_y, vec_x)
    EntitySetTransform(legment, jx, jy, targ_rot)
    if knees[i] then EntitySetTransform(knees[i], jx2, jy2) end
end

---------------------------------------------------------------------------------
--AI:
---------------------------------------------------------------------------------
local total_leglength = length*#legments --combined length of all the segments in the leg
local length_tolerance = total_leglength--how far to let the end of the leg get before re-positioning it

--what the leg needs to point at:
local tx = GetValueNumber("tx", target[1])
local ty = GetValueNumber("ty", target[2])
local distance_to_target = distance(tx, ty, target[1], target[2])

--mix target position between ex, ey and tx, ty, based on time (picks up feet slightly when stepping):
local mult = smoothness_factor * (1+(2/3))
local inv = mult-time
local mix_x = (ex/mult)*time + (tx/mult)*inv
local mix_y = (ey/mult)*time + (ty/mult)*inv

--move feet toward target, unless already within range of it, in which case snap to the coordinates:
if distance_to_target > 10 then
    target[1] = approx_rolling_average(target[1], mix_x, smoothness_factor)
    target[2] = approx_rolling_average(target[2], mix_y, smoothness_factor)
elseif target[1] ~= tx and target[2] ~= ty then
    target[1] = tx
    target[2] = ty
    --[a stepping noise could go here]
end

--if the leg stretches too far, find a new target:
if (distance(tx, ty, ex, ey) > total_leglength and distance(tx, ty, futurex, futurey) > total_leglength) or distance(tx, ty, ex, ey) == 0 then
    local surfaces_found = false
    --try to find nearby surfaces up to 3 times before resorting to stepping on air:
    for i=1,3 do
        potential_x, potential_y = (vel_x*60)+math.random(-total_leglength, total_leglength), (vel_y*60)+math.random(-total_leglength, total_leglength)
        mag = math.sqrt(((ex+potential_x)-ex)^2 + ((ey+potential_y)-ey)^2)
        potential_x, potential_y = ex + ((potential_x/mag)*total_leglength), ey + ((potential_y/mag)*total_leglength)
        did_hit, hit_x, hit_y = RaytracePlatforms(ex, ey, potential_x, potential_y)
        if did_hit then
            tx = hit_x
            ty = hit_y
            surfaces_found = true
            break
        end
    end
    --step on air:
    if not surfaces_found then
        tx = potential_x
        ty = potential_y
    end
    time = mult
end

--apply changes:
SetValueNumber("tx", tx)
SetValueNumber("ty", ty)
SetValueNumber("targ_x", target[1])
SetValueNumber("targ_y", target[2])
SetValueNumber("time", math.max(0,time-1))
```

Save this script as `IK.lua` in your mod's `files` directory. Then, save the following XML as `ik_leg.xml` in the same directory.

```xml
	<Entity name="ik_leg">

		<InheritTransformComponent>
		</InheritTransformComponent>

		<Entity tags="IK">
			<SpriteComponent
				image_file="data/entities/animals/lukki/lukki_feet/lukki_limb_a_long.png"
				z_index="1.1"
				offset_x="0"
				offset_y="5"
				>
			</SpriteComponent>
		</Entity>
		<Entity tags="knee">
			<SpriteComponent
				image_file="data/entities/animals/lukki/lukki_feet/lukki_knee.png"
				z_index="1.09"
				offset_x="5"
				offset_y="5"
				>
			</SpriteComponent>
		</Entity>
		<Entity tags="IK">
			<SpriteComponent
				image_file="data/entities/animals/lukki/lukki_feet/lukki_limb_a_long.png"
				z_index="1.1"
				offset_x="0"
				offset_y="5"
				>
			</SpriteComponent>
		</Entity>
		<Entity tags="knee">
			<SpriteComponent
				image_file="data/entities/animals/lukki/lukki_feet/lukki_knee.png"
				z_index="1.09"
				offset_x="5"
				offset_y="5"
				>
			</SpriteComponent>
		</Entity>
		<Entity tags="IK">
			<SpriteComponent
				image_file="data/entities/animals/lukki/lukki_feet/lukki_limb_b_long.png"
				z_index="1.1"
				offset_x="0"
				offset_y="5"
				>
			</SpriteComponent>
		</Entity>

		<LuaComponent
			script_source_file="yourmod/files/scripts/IK.lua"
			execute_every_n_frame="1"
			remove_after_executed="0"
			>
		</LuaComponent>
		<VariableStorageComponent
			_tags="length"
			value_int="38"
			>
		</VariableStorageComponent>
		<VariableStorageComponent
			_tags="IK_targ_x"
			value_int="30"
			>
		</VariableStorageComponent>
		<VariableStorageComponent
			_tags="IK_targ_y"
			value_int="-60"
			>
		</VariableStorageComponent>
	</Entity>
```

To add or remove limb segments, modify the number of `<Entity>` child blocks within `ik_leg.xml` that represent limb parts.

After saving the files, use Lua to spawn the `ik_leg.xml` entity and parent it to another entity:

```lua
local x, y = EntityGetTransform(entity)
local ik_leg = EntityLoad("mods/yourmod/files/ik_leg.xml", x, y)
EntityAddChild(entity, ik_leg)
```

To set the target coordinates or the length between joints, use Lua to modify the `VariableStorageComponent` values within `ik_leg.xml`:

```lua
local targcomp_x = EntityGetFirstComponent(entity, "VariableStorageComponent", "IK_targ_x")
local targcomp_y = EntityGetFirstComponent(entity, "VariableStorageComponent", "IK_targ_y")
local length_between_joints_component = EntityGetFirstComponent(entity, "VariableStorageComponent", "length")

ComponentSetValue2(targcomp_x, "value_int", whatever_number)
ComponentSetValue2(targcomp_x, "value_int", whatever_number)
ComponentSetValue2(length_between_joints_component, "value_int", whatever_number)
```

## Lua Wall: A Wall That Works Entirely Through Lua

This script creates a wall entity controlled entirely by Lua. You need to define the wall's width and height. Currently, this wall only interacts with the player character.

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id = GetUpdatedEntityID()
local x, y = EntityGetTransform(entity_id)

local players = EntityGetWithTag("player_unit")

local character_data_component = EntityGetFirstComponentIncludingDisabled(players[1], "CharacterDataComponent")
local vel_x, vel_y = ComponentGetValue2( character_data_component, "mVelocity" )
if #players > 0 then

    local player_x, player_y = EntityGetTransform(players[1])

	local old_player_x = GetValueNumber("old_player_x", player_x)
	local old_player_y = GetValueNumber("old_player_y", player_y)
	SetValueNumber("old_player_x", player_x)
	SetValueNumber("old_player_y", player_y)

    new_x = player_x
    new_y = player_y

	local variable_storage = EntityGetComponent(entity_id, "VariableStorageComponent")

	for k, v in pairs(variable_storage)do
		local name = ComponentGetValue2(v, "name")

		if(name == "top_edge")then
			top_edge = ComponentGetValue2(v, "value_string")
		elseif(name == "bottom_edge")then
			bottom_edge = ComponentGetValue2(v, "value_string")
		elseif(name == "left_edge")then
			left_edge = ComponentGetValue2(v, "value_string")
		elseif(name == "right_edge")then
			right_edge = ComponentGetValue2(v, "value_string")
		end
	end

	local old_top_edge = GetValueNumber("old_top_edge", y)
	local old_bottom_edge = GetValueNumber("old_bottom_edge", y)
	SetValueNumber("old_top_edge", y + top_edge)
	SetValueNumber("old_bottom_edge", y + bottom_edge)

	local old_left_edge = GetValueNumber("old_left_edge", x)
	local old_right_edge = GetValueNumber("old_right_edge", x)
	SetValueNumber("old_left_edge", x + left_edge)
	SetValueNumber("old_right_edge", x + right_edge)

	if ( old_player_y < y + top_edge or old_player_y > y + bottom_edge ) or ( old_top_edge > player_y ) or ( old_bottom_edge < player_y ) then

		if ( player_y > y + top_edge and player_y < y + bottom_edge ) then
			if ( player_x < x + left_edge and old_player_x > x + left_edge ) then
				EntitySetTransform(players[1], x + left_edge - 10, player_y)
			end
			if ( player_x > x + right_edge and old_player_x < x + right_edge ) then
				EntitySetTransform(players[1], x + right_edge + 10, player_y)
			end
		end
	end
end
```