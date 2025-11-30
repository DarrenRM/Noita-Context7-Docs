---
title: Gold Effect Entity
category: entities
---

# Gold Effect Entity

This entity defines a visual effect associated with the boss centipede's ending sequence, primarily focused on emitting gold and yellow sparks. It utilizes particle emitters and a homing component to create a dynamic visual display.

## Key Components

### ParticleEmitterComponent (Yellow Sparks)

This component is responsible for emitting yellow sparks.

*   **`emitted_material_name`**: `spark_yellow` - Specifies the material for the emitted particles.
*   **`gravity.y`**: `0.0` - No vertical gravity applied to the sparks.
*   **`lifetime_min`**: `5.5` - Minimum lifetime of each spark in seconds.
*   **`lifetime_max`**: `25.5` - Maximum lifetime of each spark in seconds.
*   **`count_min`**: `10` - Minimum number of sparks emitted per emission.
*   **`count_max`**: `20` - Maximum number of sparks emitted per emission.
*   **`area_circle_radius.max`**: `256` - The maximum radius of the circular area from which sparks are emitted.
*   **`airflow_force`**: `0.5` - The force applied by airflow.
*   **`attractor_force`**: `2` - The strength of any attractor forces acting on the particles.
*   **`emit_cosmetic_particles`**: `1` - Indicates that cosmetic particles should be emitted.

### ParticleEmitterComponent (Gold Particles)

This component emits gold particles, likely representing gold dust or fragments.

*   **`emitted_material_name`**: `gold` - Specifies the material for the emitted particles.
*   **`gravity.y`**: `0.0` - No vertical gravity applied to the gold particles.
*   **`lifetime_min`**: `15.5` - Minimum lifetime of each gold particle in seconds.
*   **`lifetime_max`**: `25.5` - Maximum lifetime of each gold particle in seconds.
*   **`count_min`**: `1` - Minimum number of gold particles emitted per emission.
*   **`count_max`**: `3` - Maximum number of gold particles emitted per emission.
*   **`area_circle_radius.max`**: `32` - The maximum radius of the circular area from which gold particles are emitted.
*   **`airflow_force`**: `0.5` - The force applied by airflow.
*   **`attractor_force`**: `2` - The strength of any attractor forces acting on the particles.

### VelocityComponent

Defines the basic physical properties of the entity.

*   **`gravity_y`**: `0` - No gravity affects the entity's movement.
*   **`mass`**: `0.1` - A small mass for the entity.

### HomingComponent

This component makes the entity attempt to home in on a target.

*   **`target_tag`**: `prey` - The entity will attempt to target entities with the "prey" tag.
*   **`homing_targeting_coeff`**: `30` - The coefficient determining how strongly the entity targets.
*   **`detect_distance`**: `800` - The maximum distance at which the entity can detect its target.
*   **`homing_velocity_multiplier`**: `0.9` - Multiplier for the homing velocity.

### ProjectileComponent

Configures the entity as a projectile, though with many properties set to zero, suggesting it's primarily for visual effect rather than direct damage or interaction.

*   **`speed_min` / `speed_max`**: `80` - The projectile's speed.
*   **`lifetime`**: `180` - The projectile's lifetime in seconds.
*   **`damage`**: `0` - The projectile deals no damage.
*   **`on_death_explode`**: `0` - Does not explode upon death.
*   **`on_collision_die`**: `0` - Does not die upon collision.
*   **`explosion_radius`**: `0` (within `config_explosion`) - No explosion radius.
*   **`damage`**: `0` (within `config_explosion`) - No damage from explosion.

### LuaComponent

Links the entity to a Lua script for custom behavior.

*   **`script_source_file`**: `data/entities/animals/boss_centipede/ending/sampo_normal_ending.lua` - The path to the Lua script that controls the entity's behavior.
*   **`execute_on_removed`**: `1` - The script will execute when the entity is removed.
*   **`remove_after_executed`**: `0` - The script will not remove the entity after execution.

```xml
<Entity name="unknown" >
	
	<ParticleEmitterComponent 
		emitted_material_name="spark_yellow"
		gravity.y="0.0"
		lifetime_min="5.5"
		lifetime_max="25.5"
		count_min="10"
		count_max="20"
		render_on_grid="1"
		fade_based_on_lifetime="1"
		area_circle_radius.max="256"
		cosmetic_force_create="0"
		airflow_force="0.5"
		airflow_time="0.01"
		airflow_scale="0.05"
		attractor_force="2"
		emission_interval_min_frames="1"
		emission_interval_max_frames="1"
		emit_cosmetic_particles="1"
		is_emitting="1" >
	</ParticleEmitterComponent>
	
	<ParticleEmitterComponent 
		emitted_material_name="gold"
		gravity.y="0.0"
		lifetime_min="15.5"
		lifetime_max="25.5"
		count_min="1"
		count_max="3"
		render_on_grid="1"
		fade_based_on_lifetime="1"
		area_circle_radius.max="32"
		cosmetic_force_create="0"
		airflow_force="0.5"
		airflow_time="0.01"
		airflow_scale="0.05"
		attractor_force="2"
		emission_interval_min_frames="1"
		emission_interval_max_frames="1"
		emit_cosmetic_particles="1"
		>
	</ParticleEmitterComponent>
	
	<VelocityComponent 
		gravity_y="0"
		mass="0.1"
		>
	</VelocityComponent>
	
	<HomingComponent
		target_tag="prey"
		homing_targeting_coeff="30"
		detect_distance="800"
		homing_velocity_multiplier="0.9"
		>
	</HomingComponent>

  <ProjectileComponent 
    _enabled="1" 
    lob_min="1.0"
    lob_max="1.0"
    speed_min="80"
    speed_max="80"
    friction="0"
    direction_random_rad="0"
    on_death_explode="0"
    on_death_gfx_leave_sprite="0" 
    on_lifetime_out_explode="0"
    explosion_dont_damage_shooter="1" 
    on_collision_die="0"
    lifetime="180"
    damage="0"
    velocity_sets_scale="0"
    ragdoll_force_multiplier="0"
    hit_particle_force_multiplier="0"
    camera_shake_when_shot="0" 
    bounces_left="0"
	muzzle_flash_file=""
    shoot_light_flash_radius="1"
	knockback_force="0"
	>
    <config_explosion
      never_cache="1" 
      camera_shake="0" 
      explosion_radius="0" 
      explosion_sprite="" 
      explosion_sprite_lifetime="0" 
      create_cell_probability="0" 
      hole_destroy_liquid="0"
	  explosion_sprite_emissive="0"
	  explosion_sprite_additive="0"
      hole_enabled="0" 
      ray_energy="0"
      damage="0"
      particle_effect="0" 
      damage_mortals="0"
	  physics_explosion_power.min="0" 
      physics_explosion_power.max="0"
	  physics_throw_enabled="0"
      shake_vegetation="0" 
      sparks_enabled="0" 
      stains_enabled="0" 
      >
    </config_explosion>
  </ProjectileComponent>
  
  <LuaComponent
	    execute_on_removed="1"
	    execute_every_n_frame="-1"
	    script_source_file="data/entities/animals/boss_centipede/ending/sampo_normal_ending.lua"
	    remove_after_executed="0">
  	</LuaComponent>
</Entity>
```