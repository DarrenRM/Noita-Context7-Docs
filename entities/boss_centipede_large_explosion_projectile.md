---
title: Boss Centipede Large Explosion Projectile
category: entities
---

# Boss Centipede Large Explosion Projectile

This entity defines the projectile that causes a large explosion, typically associated with the Boss Centipede in Noita. It's a projectile that detonates upon death or when its lifetime expires, creating a significant explosive effect.

## Key Components and Attributes

### Base Projectile (`Base file="data/entities/base_projectile.xml"`)

This component inherits fundamental projectile properties.

*   **`VelocityComponent`**:
    *   `gravity_y="50"`: Applies a moderate downward gravitational pull.
    *   `air_friction="-5.0"`: Reduces velocity due to air resistance.
    *   `mass="0.05"`: Defines the projectile's mass.

### Projectile (`ProjectileComponent`)

This is the core component defining the projectile's behavior and its explosive nature.

*   **`_enabled="1"`**: Enables this component.
*   **`lob_min="0.8"`, `lob_max="1.0"`**: Controls the lobbing behavior of the projectile.
*   **`speed_min="1"`, `speed_max="1"`**: Sets the projectile's speed.
*   **`direction_random_rad="0.0"`**: No randomness in projectile direction.
*   **`on_death_explode="1"`**: Triggers an explosion when the projectile dies.
*   **`on_death_gfx_leave_sprite="0"`**: Does not leave a sprite when it dies.
*   **`on_lifetime_out_explode="1"`**: Triggers an explosion when the projectile's lifetime ends.
*   **`explosion_dont_damage_shooter="1"`**: The explosion will not damage the entity that fired it.
*   **`on_collision_die="0"`**: The projectile does not die upon collision.
*   **`lifetime="5"`**: The projectile exists for 5 seconds before expiring.
*   **`damage="0"`**: The projectile itself deals no direct damage.
*   **`velocity_sets_scale="1"`**: Velocity influences scaling.
*   **`lifetime_randomness="0"`**: No randomness in lifetime.
*   **`ragdoll_force_multiplier="0.0"`**: No ragdoll force applied.
*   **`hit_particle_force_multiplier="0.0"`**: No particle force applied on hit.
*   **`camera_shake_when_shot="0"`**: No camera shake when shot.
*   **`knockback_force="0.0"`**: No knockback force applied.

#### `config_explosion`

This nested configuration defines the properties of the explosion itself.

*   **`never_cache="1"`**: Prevents caching of this explosion effect.
*   **`camera_shake="20"`**: Applies a significant camera shake of 20 units.
*   **`explosion_radius="90"`**: The explosion covers a radius of 90 units.
*   **`explosion_sprite=""`**: No specific sprite for the explosion itself.
*   **`explosion_sprite_lifetime="0"`**: The explosion sprite has no defined lifetime.
*   **`load_this_entity="data/entities/animals/boss_centipede/boss_centipede_explosion_effect.xml,data/entities/particles/particle_explosion/main_blue.xml"`**: Loads specific entities and particle effects upon explosion.
*   **`create_cell_probability="10"`**: 10% chance to create cells.
*   **`cell_explosion_power_ragdoll_coeff="0.5"`**: Coefficient for ragdoll force from cell explosions.
*   **`hole_destroy_liquid="0"`**: Does not destroy liquids.
*   **`hole_enabled="1"`**: Creates holes in terrain.
*   **`ray_energy="200000"`**: High energy for raycasting effects.
*   **`max_durability_to_destroy="15"`**: Destroys terrain up to 15 durability.
*   **`damage="1.6"`**: The explosion deals 1.6 damage.
*   **`particle_effect="1"`**: Enables particle effects for the explosion.
*   **`damage_mortals="1"`**: The explosion damages mortal entities.
*   **`physics_explosion_power.min="1.0"`, `physics_explosion_power.max="1.4"`**: Defines the range of physics-based explosion force.
*   **`physics_throw_enabled="1"`**: Physics-based throwing of objects is enabled.
*   **`shake_vegetation="1"`**: Vegetation is affected by the explosion.
*   **`spark_material="plasma_fading"`**: Sparks are made of the "plasma\_fading" material.
*   **`sparks_count_max="60"`, `sparks_count_min="50"`**: Generates 50-60 sparks.
*   **`sparks_enabled="1"`**: Sparks are enabled.
*   **`stains_enabled="1"`**: Creates stains on surfaces.
*   **`stains_radius="15"`**: Stains have a radius of 15 units.

### Light Component (`LightComponent`)

Adds a light source to the projectile.

*   **`_enabled="1"`**: Enables this component.
*   **`r="35"`, `g="210"`, `b="255"`**: Sets the light color to a bright cyan.
*   **`radius="150"`**: The light has a radius of 150 units.

### Particle Emitter Components (`ParticleEmitterComponent`)

Multiple emitters are used to create visual effects during the projectile's flight and upon explosion.

*   **`emitted_material_name="plasma_fading"`**: The particles are of the "plasma\_fading" material.
*   **`count_min`/`count_max`**: Controls the number of particles emitted.
*   **`gravity.y`**: Varies the gravitational effect on particles (positive, negative, or zero).
*   **`lifetime_min`/`lifetime_max`**: Duration of individual particles.
*   **`airflow_force`, `airflow_time`, `airflow_scale`**: Influence particle movement with airflow.
*   **`area_circle_radius.max="70"`**: Particles are emitted within a circle of this radius.
*   **`is_trail="1"`**: Creates a trail effect for some emitters.
*   **`trail_gap="0.5"`**: Spacing between trail particles.
*   **`render_on_grid="1"`**: Particles are rendered on the game grid.
*   **`fade_based_on_lifetime="1"`**: Particles fade as their lifetime ends.
*   **`create_real_particles="0"`**: Primarily cosmetic particles.
*   **`emit_cosmetic_particles="1"`**: Emits cosmetic particles.
*   **`emission_interval_min_frames`/`emission_interval_max_frames`**: Controls the frequency of particle emission.
*   **`is_emitting="1"`**: The emitter is active.
*   **Sparse Emitter**: A specific emitter designed for less frequent, longer-lasting particles with directional velocity.

### Audio Component (`AudioComponent`)

Plays a sound effect associated with the projectile.

*   **`file="data/audio/Desktop/projectiles.bank"`**: Specifies the audio bank.
*   **`event_root="player_projectiles/bullet_rocket"`**: The root event for the sound.

### Variable Storage Component (`VariableStorageComponent`)

Stores a variable related to the projectile's own file path.

*   **`name="projectile_file"`**: The name of the variable.
*   **`value_string="data/entities/animals/boss_centipede/boss_centipede_explosion_large.xml"`**: The value stored is the path to this entity's XML file.