---
title: Evil Eye Item
category: entities
---

# Evil Eye Item

This document details the configuration of the "Evil Eye" item in Noita, focusing on its attributes relevant to AI-assisted modding.

## Core Entity Configuration

The Evil Eye is an item with projectile-like physics and the ability to emit a damaging laser.

```xml
<Entity tags="hittable,teleportable_NOT,item_physics,item_pickup,evil_eye" >
	<Base file="data/entities/base_item_projectile.xml" />
    <!-- ... other components ... -->
</Entity>
```

### Key Tags:
*   `hittable`: Can be affected by projectiles.
*   `teleportable_NOT`: Cannot be teleported.
*   `item_physics`: Behaves like a physical item.
*   `item_pickup`: Can be picked up by the player.
*   `evil_eye`: Custom tag for this specific item.

## Physics Components

These components define the physical behavior of the Evil Eye.

### PhysicsBodyComponent
Governs the item's physical presence and interaction with the world.

*   `uid`: Unique identifier (1).
*   `allow_sleep`: Allows the body to sleep when inactive (1).
*   `angular_damping`: Resistance to rotation (0.95).
*   `linear_damping`: Resistance to linear movement (0).
*   `fixed_rotation`: Prevents rotation (0).
*   `is_bullet`: Treats the body as a bullet for collision purposes (1).
*   `hax_fix_going_through_ground`: Fixes a bug where the item might pass through the ground.

### PhysicsImageShapeComponent
Defines the visual shape and material for physics interactions.

*   `body_id`: Links to the `PhysicsBodyComponent` (1).
*   `image_file`: Specifies the visual sprite (`data/items_gfx/evil_eye.png`).
*   `material`: The physics material (`item_box2d_meat`).

### PhysicsThrowableComponent
Enables the item to be thrown.

*   `max_throw_speed`: Maximum speed when thrown (180).
*   `throw_force_coeff`: Coefficient for throw force (1.25).
*   `min_torque`: Minimum torque applied when thrown (0.1).
*   `max_torque`: Maximum torque applied when thrown (1).

### VelocityComponent
Manages the item's velocity.

*   `_tags="enabled_in_world"`: Active when the item is in the game world.

## Plasma Functionality (Laser Emission)

This section configures the Evil Eye's primary offensive capability: a damaging laser.

```xml
	<Entity>
		<LaserEmitterComponent
			_enabled="0">
			<laser
				is_emitting="0"
				damage_to_entities="0.06"
				damage_to_cells="2500"
				max_length="54"
				beam_radius="2.5"
				max_cell_durability_to_destroy="11"
				root_entity_is_responsible_for_damage="1"
				audio_enabled="0"
				audio_hit_always_enabled="1"
				hit_particle_chance="40"
				beam_particle_chance="80"
				beam_particle_type="spark_red_bright"
				>
			</laser>
		</LaserEmitterComponent>
		<SpriteComponent
			_enabled="0"
			_tags="enabled_in_world,enabled_in_hand"
			image_file="data/projectiles_gfx/orb_red.xml"
			alpha="0.7"
			additive="1"
			emissive="1"
			>
		</SpriteComponent>
	</Entity>
```

### LaserEmitterComponent
Controls the laser's properties.

*   `_enabled`: Initially disabled (0).
*   `laser`:
    *   `damage_to_entities`: Damage per tick to entities (0.06).
    *   `damage_to_cells`: Damage per tick to environment cells (2500).
    *   `max_length`: Maximum range of the laser (54).
    *   `beam_radius`: Width of the laser beam (2.5).
    *   `max_cell_durability_to_destroy`: How much cell durability is removed per tick (11).
    *   `hit_particle_chance`: Chance to spawn particles on hit (40).
    *   `beam_particle_type`: Type of particle for the beam (`spark_red_bright`).

### SpriteComponent (Laser Visual)
Defines the visual representation of the laser when active.

*   `image_file`: Sprite for the laser (`data/projectiles_gfx/orb_red.xml`).
*   `alpha`: Transparency (0.7).
*   `additive`, `emissive`: Rendering properties for a glowing effect.

## Item Components

These components define the item's properties when held or in the inventory.

### ItemComponent
Core properties for the item.

*   `item_name`: Localized name (`$item_evil_eye`).
*   `is_pickable`: Can be picked up (1).
*   `is_equipable_forced`: Can be equipped directly (1).
*   `ui_sprite`: Path to the UI icon (`data/ui_gfx/items/evil_eye.png`).
*   `ui_description`: Localized description (`$item_description_evil_eye`).
*   `preferred_inventory`: Default inventory slot (`QUICK`).

### UIInfoComponent
Provides information for the UI.

*   `name`: Display name (`$item_evil_eye`).

### AbilityComponent
Defines abilities associated with the item.

*   `throw_as_item`: Allows throwing the item (1).

## Scripting Components

Lua scripts handle the item's dynamic behavior.

### LuaComponent (State Management)
Manages the state transitions and logic of the Evil Eye.

*   `_tags="enabled_in_hand"`: Active when held.
*   `script_enabled_changed`: Script to run when the item's enabled state changes (`data/scripts/items/evil_eye_state.lua`).
*   `execute_every_n_frame="-1"`: Executes only on state changes.

### LuaComponent (Beam Logic)
Handles the actual laser beam activation and firing.

*   `_tags="enabled_in_hand"`: Active when held.
*   `_enabled="0"`: Initially disabled.
*   `script_source_file`: Path to the script (`data/scripts/items/evil_eye_beam.lua`).
*   `execute_every_n_frame="1"`: Executes every frame when enabled.

## Visual and Effect Components

These components add visual flair and particle effects.

### SpriteComponent (Handheld)
The visual representation of the Evil Eye when held by the player.

*   `_tags="enabled_in_hand,evil_eye_in_hand"`: Active when held.
*   `image_file`: Sprite for the handheld item (`data/items_gfx/evil_eye.png`).
*   `offset_x`, `offset_y`: Position adjustments.

### SpriteComponent (Iris)
A temporary sprite for the iris effect, removed when the laser is first activated.

*   `_tags="enabled_in_world,enabled_in_hand"`: Active when in world or hand.
*   `image_file`: Sprite for the iris (`data/items_gfx/evil_eye_iris.png`).
*   `z_index`: Rendering layer (-1.6).
*   `offset_x`, `offset_y`: Position adjustments.

### SpriteParticleEmitterComponent
Emits particles that resemble a ray or beam.

*   `sprite_file`: Particle sprite (`data/particles/ray.xml`).
*   `color.r`, `color.g`, `color.b`, `color.a`: Initial color (reddish-purple).
*   `color_change.a`: Alpha change over lifetime (-3.5).
*   `scale.x`, `scale.y`: Initial scale (1, 0).
*   `scale_velocity.x`, `scale_velocity.y`: Scale change over lifetime (-0.3, 3).
*   `emission_interval_min_frames`, `emission_interval_max_frames`: Emission frequency.
*   `emissive`, `additive`: Rendering properties.
*   `randomize_position`, `randomize_velocity`: Controls particle spread.
*   `velocity_always_away_from_center`: Particles move away from the emitter's center.

### LightComponent
Adds a light source when the item is active.

*   `_tags="enabled_in_world,enabled_in_hand,magic_eye_check"`: Active when in world or hand, and potentially checked by other magic effects.
*   `radius`: Light radius (60).
*   `r`, `g`, `b`: Light color (reddish).

### ParticleEmitterComponent
Emits cosmetic particles around the item.

*   `emitted_material_name`: Particle type (`spark_red`).
*   `x_vel_min`, `x_vel_max`, `y_vel_min`, `y_vel_max`: Velocity range for particles.
*   `velocity_always_away_from_center`: Particles move away from the emitter.
*   `count_min`, `count_max`: Number of particles emitted.
*   `lifetime_min`, `lifetime_max`: Particle lifespan.
*   `emission_interval_min_frames`, `emission_interval_max_frames`: Emission frequency.
*   `is_emitting`: Whether particles are currently emitted (1).