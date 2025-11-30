---
title: Orbit Nuke Projectile
category: entities
---

# Orbit Nuke Projectile

This entity defines the behavior and appearance of the "Orbit Nuke" projectile in Noita. It's a powerful projectile designed to explode on impact or after a set lifetime, causing significant damage and environmental destruction.

## Key Components and Attributes

### Entity Definition

*   **`name`**: `$projectile_default` (This is a placeholder, the actual name is derived from its usage context).
*   **`tags`**: `nuke`, `orbit_projectile` - These tags categorize the entity for game logic and modding.

### Base Projectile (`Base file="data/entities/base_projectile.xml"`)

This component inherits fundamental projectile properties.

*   **`VelocityComponent`**:
    *   `gravity_y="0"`: The projectile is not affected by gravity.
    *   `air_friction="0"`: No air resistance.
    *   `mass="0.2"`: Defines the projectile's mass.

### Projectile Component (`ProjectileComponent`)

This is the core component defining the nuke's projectile behavior.

*   **`_enabled="1"`**: Enables this component.
*   **`lob_min="0.8"`, `lob_max="1.0"`**: Controls the lobbing behavior (how much it arcs).
*   **`speed_min="0"`, `speed_max="0"`**: The projectile has no initial speed, likely meaning it's spawned with a specific velocity.
*   **`direction_random_rad="0.01"`**: A small amount of randomness in its initial direction.
*   **`on_death_explode="1"`**: The projectile explodes when it dies (e.g., on collision or lifetime out).
*   **`on_death_gfx_leave_sprite="0"`**: Does not leave behind its sprite graphic upon death.
*   **`on_lifetime_out_explode="1"`**: Explodes when its lifetime expires.
*   **`explosion_dont_damage_shooter="0"`**: The explosion can damage the entity that shot it.
*   **`on_collision_die="1"`**: The projectile dies upon colliding with something.
*   **`lifetime="7200"`**: The maximum lifetime of the projectile in frames (approximately 2 minutes).
*   **`damage="2"`**: Base damage dealt by the projectile itself (before explosion).
*   **`velocity_sets_scale="1"`**: Velocity influences the projectile's scale.
*   **`lifetime_randomness="7"`**: Adds a small random variation to the lifetime.
*   **`ragdoll_force_multiplier="0.04"`**: Affects how much force is applied to ragdolls upon explosion.
*   **`hit_particle_force_multiplier="5.5"`**: Influences the force of particles created on impact.
*   **`camera_shake_when_shot="5.0"`**: Triggers camera shake when the projectile is fired.
*   **`muzzle_flash_file="data/entities/particles/muzzle_flashes/muzzle_flash_launcher_large.xml"`**: Specifies the muzzle flash particle effect.
*   **`shoot_light_flash_r="255"`, `shoot_light_flash_g="210"`, `shoot_light_flash_b="40"`**: Defines the color of the light flash when shot (yellowish).
*   **`shoot_light_flash_radius="130"`**: The radius of the light flash.
*   **`knockback_force="1.5"`**: The force that pushes entities away upon impact.

#### `config_explosion`

This nested element defines the properties of the explosion.

*   **`never_cache="1"`**: Prevents caching of this explosion for performance.
*   **`camera_shake="60"`**: Significant camera shake upon explosion.
*   **`explosion_radius="150"`**: The radius of the explosion's effect.
*   **`explosion_sprite="data/particles/explosion_032.xml"`**: The sprite used for the explosion visual.
*   **`load_this_entity="data/entities/particles/particle_explosion/main_large.xml,data/entities/misc/loose_chunks.xml"`**: Entities to load and spawn during the explosion (large explosion particles and loose chunks).
*   **`explosion_sprite_lifetime="0"`**: The explosion sprite has no independent lifetime.
*   **`create_cell_probability="5"`**: Probability of creating new cells (environmental destruction).
*   **`hole_destroy_liquid="0"`**: Does not destroy liquids.
*   **`hole_enabled="1"`**: Creates holes in terrain.
*   **`ray_energy="4700000"`**: High energy for destructive rays.
*   **`damage="6"`**: Damage dealt by the explosion.
*   **`particle_effect="1"`**: Enables particle effects for the explosion.
*   **`damage_mortals="1"`**: The explosion damages living entities.
*   **`physics_explosion_power.min="4.5"`, `physics_explosion_power.max="9"`**: The force of the physics-based explosion.
*   **`shake_vegetation="1"`**: Causes vegetation to shake.
*   **`sparks_count_max="200"`, `sparks_count_min="400"`**: Number of sparks generated.
*   **`sparks_enabled="1"`**: Sparks are enabled.
*   **`stains_enabled="1"`**: Creates stains on surfaces.
*   **`stains_radius="25"`**: The radius of the stains.
*   **`background_lightning_count="5"`**: Spawns background lightning effects.
*   **`max_durability_to_destroy="12"`**: The maximum durability of objects that can be destroyed by the explosion.
*   **`audio_event_name="explosions/nuke"`**: The sound event played for the explosion.

### Sprite Component (`SpriteComponent`)

Defines the visual appearance of the nuke.

*   **`_enabled="1"`**: Enables this component.
*   **`alpha="1"`**: Fully opaque.
*   **`image_file="data/projectiles_gfx/nuke.xml"`**: The sprite sheet or animation file for the nuke.
*   **`offset_x="2"`, `offset_y="2"`**: Offsets the sprite's position.

### Particle Emitter Components (`ParticleEmitterComponent`)

These components spawn various particle effects.

1.  **Spark Emitter**:
    *   `emitted_material_name="spark"`: Spawns "spark" particles.
    *   `is_trail="1"`: Creates a trail effect.
    *   `create_real_particles="0"`: Spawns cosmetic particles.
    *   `emission_interval_min_frames="1"`, `emission_interval_max_frames="1"`: Emits particles every frame.

2.  **Smoke Emitter**:
    *   `emitted_material_name="smoke"`: Spawns "smoke" particles.
    *   `create_real_particles="1"`: Spawns actual game particles.
    *   `x_vel_min="-50"`, `x_vel_max="5"`: Wide range of horizontal velocity.

3.  **Radioactive Liquid Fading Emitter**:
    *   `emitted_material_name="radioactive_liquid_fading"`: Spawns particles representing radioactive liquid.
    *   `create_real_particles="1"`: Spawns actual game particles.
    *   `emission_interval_min_frames="0"`, `emission_interval_max_frames="4"`: Emits particles with a slight delay.

### Audio Loop Component (`AudioLoopComponent`)

*   **`file="data/audio/Desktop/projectiles.bank"`**: The audio bank containing the sound.
*   **`event_name="projectiles/rocket_passby"`**: The specific sound event to play.
*   **`auto_play="1"`**: The sound plays automatically when the entity is active.

### Variable Storage Component (`VariableStorageComponent`)

*   **`name="projectile_file"`**: Stores a string variable.
*   **`value_string="data/entities/projectiles/deck/nuke.xml"`**: The value of the variable, likely referencing another entity file for more complex projectile behavior or deck integration.

---