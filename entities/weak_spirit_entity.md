---
title: Weak Spirit Entity
category: entities
---

# Weak Spirit Entity

This document details the `weakspirit.xml` entity, a flying, ethereal creature in Noita. It focuses on key attributes relevant to AI modding.

## Core Attributes

The Weak Spirit is a basic flying enemy with low health and no direct offensive capabilities. Its primary function seems to be atmospheric or a minor nuisance.

### `Base` Entity Configuration

The entity inherits from `base_enemy_flying.xml`, indicating its flying nature and standard enemy behaviors.

### `AnimalAIComponent`

This component governs the creature's AI and behavior.

*   **`preferred_job`**: `JobDefault` - Standard AI job.
*   **`escape_if_damaged_probability`**: `35` - Has a 35% chance to attempt to flee when damaged.
*   **`attack_melee_damage_min` / `max`**: `0.6` / `0.8` - While melee attacks are disabled, these define a potential damage range.
*   **`creature_detection_range_x` / `y`**: `250` - Detects creatures within a 250-unit radius.
*   **`food_material`**: `meat` - Indicates its biological classification.
*   **`needs_food`**: `0` - Does not require food to survive.
*   **`sense_creatures`**: `1` - Actively senses other creatures.
*   **`can_fly`**: `1` - Confirms its ability to fly.

### `DamageModelComponent`

Defines the entity's health and damage resistances/vulnerabilities.

*   **`hp`**: `3` - Very low health pool.
*   **`ragdoll_material`**: `rock_static_glow` - The material used for its ragdoll effect.
*   **`blood_material`**: `plasma_fading` - The material of its "blood" effect.
*   **`air_needed`**: `0` - Does not require air.

#### `damage_multipliers`

*   **`projectile`**: `0.8` - Takes 80% damage from projectiles.
*   **`explosion`**: `0.8` - Takes 80% damage from explosions.
*   **`slice`**: `0.4` - Takes 40% damage from slicing.
*   **`holy`**: `1.2` - Takes 120% damage from holy sources.

### `SpriteComponent`

Determines the visual representation of the entity.

*   **`image_file`**: `data/enemies_gfx/weakspirit.xml` - Points to the sprite definition.
*   **`additive`**: `1` - Uses additive blending for rendering.
*   **`emissive`**: `1` - The sprite emits light.

### `PathFindingComponent`

Defines how the entity navigates the environment.

*   **`can_fly`**: `1` - Explicitly allows flight.
*   **`can_swim_on_surface`**: `1` - Can swim on the surface of liquids.

### `GenomeDataComponent`

Classifies the entity within the game's ecosystem.

*   **`herd_id`**: `ghost` - Identifies its group.
*   **`food_chain_rank`**: `15` - Its position in the food chain.
*   **`is_predator`**: `1` - Classified as a predator.

### `CharacterPlatformingComponent`

Controls movement physics, though less relevant for a flying entity.

*   **`pixel_gravity`**: `600` - Standard gravity value.
*   **`jump_velocity_y`**: `0` - Cannot jump.
*   **`run_velocity`**: `0` - Cannot run.

### `HitboxComponent` & `CharacterDataComponent`

Define the collision and physical boundaries of the entity.

*   **`aabb_min_x`/`max_x`**, **`aabb_min_y`/`max_y`**: `-3.5` to `3.5` - Small bounding box.
*   **`mass`**: `1.0` - Standard mass.

## Special Components

### `AudioComponent` & `AudioLoopComponent`

Handles sound effects.

*   **`file`**: `data/audio/Desktop/animals.bank` - The audio bank used.
*   **`event_root`**: `animals/ghost` - Base event name for its sounds.
*   **`event_name`**: `animals/ghost/movement_loop` - Specific event for its movement loop.

### `GameEffectComponent`

Applies passive effects to the entity.

*   **`effect`**: `PROTECTION_FREEZE` - Grants immunity to freezing.
*   **`frames`**: `-1` - The effect is permanent.

### `LuaComponent`

Attaches custom Lua scripting.

*   **`script_source_file`**: `data/scripts/animals/spirit_aura_weak.lua` - The script responsible for its unique behaviors (likely an aura effect).
*   **`execute_every_n_frame`**: `101` - The script runs periodically.

### `ParticleEmitterComponent`

Generates visual particle effects.

*   **`emitted_material_name`**: `spark_blue` - Emits blue sparks.
*   **`lifetime_min`/`max`**: `0.5` to `1.2` - Particles last between 0.5 and 1.2 seconds.
*   **`count_min`/`max`**: `20` to `30` - Emits 20-30 particles per burst.
*   **`area_circle_radius.min`/`max`**: `32` to `72` - Particles are emitted within a circular area.
*   **`velocity_always_away_from_center`**: `240` - Particles are strongly pushed away from the emitter's center.

```xml
<Entity tags="glue_NOT" name="$animal_weakspirit" >
	<Base file="data/entities/base_enemy_flying.xml" >
		<ItemChestComponent level="5" enemy_drop="1" > </ItemChestComponent>
		<AnimalAIComponent 
			_enabled="1" 
			preferred_job="JobDefault"
			escape_if_damaged_probability="35"
			attack_ranged_min_distance="0"
			attack_melee_damage_min="0.6" 
			attack_melee_damage_max="0.8"
			attack_dash_enabled="0"
			attack_melee_enabled="0"
			creature_detection_range_x="250"
			creature_detection_range_y="250"
			food_material="meat"
			needs_food="0"
			sense_creatures="1"
			attack_ranged_enabled="0"
			can_fly="1"  
			>
		</AnimalAIComponent>
		<DamageModelComponent 
			hp="3"
			physics_objects_damage="0"
			ragdoll_filenames_file=""
			fire_probability_of_ignition="0" 
			ragdoll_fx_forced="DISINTEGRATED"
			ragdoll_material="rock_static_glow"
			blood_material="plasma_fading"
			blood_spray_material="plasma_fading"
			blood_sprite_directional=""
			blood_sprite_large=""
			air_needed="0"
			>
			<damage_multipliers
				projectile="0.8"
				explosion="0.8"
				electricity="1"
				fire="0" 
				slice="0.4"
				holy="1.2"
				>
			</damage_multipliers>
		</DamageModelComponent>
		<SpriteComponent 
			image_file="data/enemies_gfx/weakspirit.xml" 
			offset_x="0"
			offset_y="0"
			additive="1"
			emissive="1"
			>
		</SpriteComponent>
		<PathFindingComponent
		    can_swim_on_surface="1"
			frames_to_get_stuck="20"
			can_fly="1"
			can_jump="0" >
		</PathFindingComponent>
		<PathFindingGridMarkerComponent
			marker_work_flag="16" >
		</PathFindingGridMarkerComponent>
		<GenomeDataComponent 
			herd_id="ghost"
			food_chain_rank="15"
			is_predator="1" >
		</GenomeDataComponent>
		<CharacterPlatformingComponent 
    		pixel_gravity="600" 
			jump_velocity_y="0" 
			run_velocity="0"
			>
		</CharacterPlatformingComponent>
		<CameraBoundComponent
		  max_count="30"
		  distance="160000">
		</CameraBoundComponent>
		<HitboxComponent 
		  _enabled="1" 
		  aabb_min_x="-3.5" 
		  aabb_max_x="3.5" 
		  aabb_min_y="-3.5" 
		  aabb_max_y="3.5" 
		  >
		</HitboxComponent>
		<CharacterDataComponent 
			collision_aabb_min_x="-3.5"
			collision_aabb_max_x="3.5"  
			collision_aabb_min_y="-3.5"
			collision_aabb_max_y="3.5"
			mass="1.0"
			>
		</CharacterDataComponent>
		<AudioComponent
			file="data/audio/Desktop/animals.bank"
			event_root="animals/ghost" >
		</AudioComponent>
	</Base>
	<AudioLoopComponent
		file="data/audio/Desktop/animals.bank"
		event_name="animals/ghost/movement_loop"
		set_speed_parameter="1"
		auto_play="1">
	</AudioLoopComponent>
	<Entity>
		<InheritTransformComponent />
	    <GameEffectComponent 
	        effect="PROTECTION_FREEZE"
	        frames="-1"
	    >
		</GameEffectComponent >
	</Entity>
	<LuaComponent
		script_source_file="data/scripts/animals/spirit_aura_weak.lua"
		execute_every_n_frame="101"
		>
	</LuaComponent>
	<ParticleEmitterComponent 
		emitted_material_name="spark_blue"
		gravity.y="0.0"
		lifetime_min="0.5"
		lifetime_max="1.2"
		count_min="20"
		count_max="30"
		render_on_grid="1"
		fade_based_on_lifetime="1"
		area_circle_radius.min="32"
		area_circle_radius.max="72"
		cosmetic_force_create="0"
		airflow_force="1.5"
		airflow_time="1.9"
		airflow_scale="0.15"
		emission_interval_min_frames="1"
		emission_interval_max_frames="1"
		emit_cosmetic_particles="1"
		draw_as_long="1"
		x_vel_min="-1"
		x_vel_max="1"
		y_vel_min="-1"
		y_vel_max="1"
		is_emitting="1" 
		velocity_always_away_from_center="240"
		>
	</ParticleEmitterComponent>
</Entity>
```