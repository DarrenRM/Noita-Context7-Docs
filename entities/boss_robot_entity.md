---
title: Boss Robot Entity
category: entities
---

# Boss Robot Entity

This document details the configuration of the Boss Robot entity in Noita, focusing on key components relevant to AI-assisted modding.

## Core Entity Properties

The `Entity` tag defines the fundamental properties and tags associated with the Boss Robot.

```xml
<Entity tags="enemy,mortal,human,hittable,homing_target,teleportable_NOT,boss,polymorphable_NOT,miniboss,music_energy_100,necrobot_NOT,glue_NOT" name="$animal_boss_robot">
```

**Key Tags:**

*   `enemy`: Identifies the entity as an enemy.
*   `mortal`: The entity can be killed.
*   `hittable`: The entity can be targeted and damaged.
*   `homing_target`: Allows for homing projectiles to target it.
*   `boss`: Designates it as a boss entity.
*   `miniboss`: Designates it as a miniboss entity.
*   `music_energy_100`: Likely influences in-game music cues.
*   `teleportable_NOT`, `polymorphable_NOT`, `necrobot_NOT`, `glue_NOT`: These tags explicitly prevent certain interactions.

## Visual Components

### SpriteComponent

Defines the visual representation of the Boss Robot.

```xml
<SpriteComponent 
	_tags="character"
	image_file="data/entities/animals/boss_robot/body.xml" 
	offset_y="24"
	offset_x="24" >
</SpriteComponent>
```

*   `image_file`: Points to the XML file defining the sprite's appearance.
*   `offset_y`, `offset_x`: Adjusts the sprite's position relative to the entity's origin.

### LightComponent

Adds a light source emanating from the Boss Robot.

```xml
<LightComponent 
	_enabled="1" 
	radius="256"
	r="100"
	g="255"
	b="130"
	offset_y="0"
	fade_out_time="1.5" >
</LightComponent>
```

*   `radius`: The range of the light.
*   `r`, `g`, `b`: RGB color values for the light.
*   `fade_out_time`: How long the light takes to fade.

## AI and Pathfinding

### LimbBossComponent

Likely controls the behavior and state management of the boss's limbs or segments.

```xml
<LimbBossComponent
	state="1"
	>
</LimbBossComponent>
```

*   `state`: The initial state of the component.

### PathFindingComponent

Governs how the Boss Robot navigates the game world.

```xml
<PathFindingComponent 
	can_dive="1" 
	can_fly="1" 
	can_jump="0" 
	can_walk="0" 
	cost_of_flying="500" 
	initial_jump_max_distance_x="100" 
	initial_jump_max_distance_y="60" 
	jump_speed="200" 
	max_jump_distance_from_camera="400" >
</PathFindingComponent>
```

**Key Attributes:**

*   `can_dive`, `can_fly`: Enables specific movement types.
*   `can_jump`, `can_walk`: Disables certain movement types.
*   `cost_of_flying`: The perceived cost of using flight for pathfinding.
*   `initial_jump_max_distance_x`, `initial_jump_max_distance_y`: Defines the maximum horizontal and vertical distance for initial jumps.
*   `jump_speed`: The speed at which the entity jumps.
*   `max_jump_distance_from_camera`: Limits jumps based on camera proximity.

### PathFindingGridMarkerComponent

Helps the pathfinding system understand the entity's position on the navigation grid.

```xml
<PathFindingGridMarkerComponent 
	_enabled="1" 
	marker_offset_x="0" 
	marker_offset_y="-6" 
	marker_work_flag="16" >
</PathFindingGridMarkerComponent>
```

*   `marker_offset_y`: Adjusts the marker's vertical position.
*   `marker_work_flag`: A flag used by the pathfinding system.

## Physics and Collision

### PhysicsAIComponent

Manages the physics simulation and AI-driven forces applied to the entity.

```xml
<PhysicsAIComponent
	target_vec_max_len="15.0"
	force_coeff="10.0"
	force_balancing_coeff="0.8"
	force_max="100"
	torque_coeff="50"
	torque_balancing_coeff="4"
	torque_max="50.0" >
</PhysicsAIComponent>
```

*   `target_vec_max_len`: Maximum length of the target vector for AI forces.
*   `force_coeff`, `force_max`: Controls the strength and maximum of applied forces.
*   `torque_coeff`, `torque_max`: Controls the strength and maximum of applied rotational forces.

### PhysicsBodyComponent

Defines the physical properties of the entity's body.

```xml
<PhysicsBodyComponent 
	angular_damping="0.02" 
	fixed_rotation="1" 
	linear_damping="0"  >
</PhysicsBodyComponent>
```

*   `fixed_rotation`: Prevents the entity from rotating freely.
*   `angular_damping`, `linear_damping`: Resistances to rotational and linear motion.

### PhysicsShapeComponent

Defines the collision shape of the entity.

```xml
<PhysicsShapeComponent
	is_circle="1"
	radius_x="18"
	radius_y="18"
	friction="0.0"
	restitution="0.3" >
</PhysicsShapeComponent>
```

*   `is_circle`: Specifies a circular collision shape.
*   `radius_x`, `radius_y`: The radii of the circle.
*   `friction`, `restitution`: Physical properties affecting collisions.

## Damage and Health

### DamageModelComponent

Handles health, damage taken, and how the entity reacts to damage.

```xml
<DamageModelComponent 
	hp="50" 
	air_needed="0" 
	falling_damages="0" 
	fire_damage_amount="0.2" 	 
	blood_material="liquid_fire"
	materials_damage="1" 
	materials_that_damage="lava,magic_liquid_mana_regeneration" 
	ragdoll_material="steel" >
	<damage_multipliers
		melee="0"
		projectile="0"
		explosion="0"
		electricity="0.8"
		fire="0"
		slice="0.6"
		>
	</damage_multipliers>
</DamageModelComponent>
```

**Key Attributes:**

*   `hp`: The entity's hit points.
*   `blood_material`: The material that appears when the entity is damaged.
*   `materials_that_damage`: Materials that can damage the entity.
*   `damage_multipliers`: Modifiers for different damage types.

### GenomeDataComponent

Defines the entity's role in the ecosystem and its behavior towards other entities.

```xml
<GenomeDataComponent 
	food_chain_rank="5" 
	herd_id="robot" 
	is_predator="1" >
</GenomeDataComponent>
```

*   `food_chain_rank`: Its position in the food chain.
*   `herd_id`: Identifies its group or type.
*   `is_predator`: Indicates if it hunts other entities.

### HitboxComponent

Defines the primary hitbox for damage detection.

```xml
<HitboxComponent 
	_tags="hitbox_default"
	aabb_min_x="-18" 
	aabb_max_x="18" 
	aabb_min_y="-18" 
	aabb_max_y="18"
	damage_multiplier="1.0" >
</HitboxComponent>
```

*   `aabb_min_x`, `aabb_max_x`, `aabb_min_y`, `aabb_max_y`: Defines the bounding box of the hitbox.

## Other Components

### AudioComponent

Manages sound effects associated with the entity.

```xml
<AudioComponent 
	file="data/audio/Desktop/animals.bank"
	event_root=""
	set_latest_event_position="1" >
</AudioComponent>
```

*   `file`: The audio bank file.
*   `event_root`: The base event name for sounds.

### SpriteAnimatorComponent

Handles sprite animations.

```xml
<SpriteAnimatorComponent 
	rotate_to_surface_normal="0" 
	target_sprite_comp_name="character" >
</SpriteAnimatorComponent>
```

*   `target_sprite_comp_name`: The name of the sprite component to animate.

### CellEaterComponent

Allows the entity to consume materials from the environment.

```xml
<CellEaterComponent
	radius="30"
	ignored_material="aluminium_robot"
	eat_probability="100">
</CellEaterComponent>
```

*   `radius`: The area around the entity where it can eat.
*   `ignored_material`: Materials that the entity will not eat.

### Health Bar Components

These components are responsible for displaying the Boss Robot's health bar.

```xml
<SpriteComponent 
	_tags="health_bar_back,ui"
	image_file="data/ui_gfx/health_slider_back.png" 
	z_index="-9000" >
</SpriteComponent>

<SpriteComponent 
	_tags="health_bar,ui" 
	image_file="data/ui_gfx/health_slider_front.png" 
	z_index="-9000" >
</SpriteComponent>
	
<BossHealthBarComponent>
</BossHealthBarComponent>
```

### LuaComponent (Death)

Links to a Lua script that executes when the entity dies.

```xml
<LuaComponent
	script_death="data/entities/animals/boss_robot/death.lua"
	>
</LuaComponent>
```

### AudioComponent (Boss Specific)

A separate audio component for boss-specific sounds.

```xml
<AudioComponent
	file="data/audio/Desktop/animals.bank"
	event_root="animals/robot">
</AudioComponent>
```

## Limbs and Spell Eater

### Limbs

The Boss Robot is composed of multiple `limb.xml` entities, suggesting a segmented or modular structure.

```xml
<Entity>  <Base file="data/entities/animals/boss_robot/limb.xml" />  </Entity>
<!-- ... multiple instances ... -->
```

### Spell Eater Entity

This nested entity handles the Boss Robot's spell-eating ability, including particle effects.

```xml
<Entity>
	<InheritTransformComponent only_position="1" />
	<LuaComponent script_source_file="data/entities/animals/boss_robot/spell_eater.lua" execute_every_n_frame="1" />
	
	<!-- ParticleEmitterComponents for spell eating effects -->
	<ParticleEmitterComponent _tags="boss_robot_spell_eater" emitted_material_name="spark_red" ... />
	<ParticleEmitterComponent _tags="boss_robot_spell_eater" emitted_material_name="spark_red" ... />
	<ParticleEmitterComponent _tags="boss_robot_spell_eater" emitted_material_name="spark_red" ... />
</Entity>
```

*   `spell_eater.lua`: The script controlling the spell-eating logic.
*   `ParticleEmitterComponent`: Defines the visual particles associated with spell eating.

## Variable Storage and State Management

### VariableStorageComponent

Used to store and manage internal states and variables for the Boss Robot.

```xml
<VariableStorageComponent name="state" value_int="0" ></VariableStorageComponent>
<VariableStorageComponent name="spell_eater" value_int="1" ></VariableStorageComponent>
<VariableStorageComponent name="laser_angle" value_float="0" ></VariableStorageComponent>
```

*   `state`: Likely tracks the overall AI state.
*   `spell_eater`: Indicates if the spell-eating mechanism is active.
*   `laser_angle`: Stores the current angle of its laser attacks.

### LuaComponent (State)

Manages the Boss Robot's AI state transitions and behaviors.

```xml
<LuaComponent
	script_source_file="data/entities/animals/boss_robot/state.lua"
	execute_every_n_frame="40"
	>
</LuaComponent>
```

*   `state.lua`: The primary AI script for the boss.
*   `execute_every_n_frame`: How often the script's logic is executed.

## Attack Components

### LaserEmitterComponent

Defines the entity's laser attack capabilities. Multiple instances suggest multiple laser emitters.

```xml
<LaserEmitterComponent
	is_emitting="0"
	laser_angle_add_rad="0"
	>
	<laser
		damage_to_entities="0.8"
		max_cell_durability_to_destroy="14"
		damage_to_cells="50000"
		max_length="240"
		beam_radius="10.5"
		hit_particle_chance="20"
		beam_particle_chance="100"
		beam_particle_type="spark_red"
		audio_enabled="1"
		>
	</laser>
</LaserEmitterComponent>
```

**Key Laser Attributes:**

*   `is_emitting`: Whether the laser is currently active.
*   `damage_to_entities`: Damage dealt to entities.
*   `damage_to_cells`: Damage dealt to the environment.
*   `max_length`: The maximum range of the laser.
*   `beam_radius`: The width of the laser beam.

## Buffs and Effects

### GameEffectComponent

Applies a persistent game effect to the entity.

```xml
<Entity>
	<InheritTransformComponent />
    <GameEffectComponent 
        effect="PROTECTION_PROJECTILE"
        frames="-1"
    >
	</GameEffectComponent >
</Entity>
```

*   `effect="PROTECTION_PROJECTILE"`: Grants immunity or resistance to projectiles.
*   `frames="-1"`: The effect is permanent.