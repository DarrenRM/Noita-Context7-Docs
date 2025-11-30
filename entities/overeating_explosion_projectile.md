---
title: Overeating Explosion Projectile
category: entities
---

# Overeating Explosion Projectile

This entity defines a projectile that explodes upon death, either from low velocity or after a set lifetime. It's designed to create a significant visual and physical impact.

## Key Components

### Base Projectile (`<Base file="data/entities/base_projectile.xml">`)

*   **`gravity_y="100"`**: Applies a moderate downward gravitational pull to the projectile.

### Projectile Component (`<ProjectileComponent>`)

This is the core component defining the projectile's behavior.

*   **`lob_min="0.8"`, `lob_max="1.0"`**: Controls the arc of the projectile's trajectory. Values closer to 1.0 result in a flatter arc.
*   **`speed_min="160"`, `speed_max="170"`**: Sets the initial velocity range of the projectile.
*   **`on_death_explode="1"`**: Triggers an explosion when the projectile dies.
*   **`on_lifetime_out_explode="1"`**: Triggers an explosion when the projectile's lifetime expires.
*   **`die_on_low_velocity="1"`**: Causes the projectile to die (and explode) if its speed drops below a certain threshold.
*   **`damage="0.5"`**: The base damage dealt by the projectile itself before any explosion effects.
*   **`on_collision_die="1"`**: The projectile will die upon colliding with something.
*   **`lifetime="1"`**: The maximum duration in seconds the projectile will exist before expiring.

#### Explosion Configuration (`<config_explosion>`)

Defines the parameters of the explosion effect.

*   **`camera_shake="40"`**: The intensity of camera shake experienced by players near the explosion.
*   **`explosion_radius="60"`**: The area of effect for the explosion.
*   **`explosion_sprite="data/particles/explosion_025_fuel.xml"`**: The visual sprite used for the explosion effect.
*   **`load_this_entity="data/entities/particles/particle_explosion/main_guts.xml"`**: Specifies an entity to be loaded and spawned at the explosion's center, likely for more complex particle effects.
*   **`hole_enabled="1"`**: Enables the creation of holes in surfaces hit by the explosion.
*   **`hole_image="data/temp/explosion_hole.png"`**: The image used for the explosion-created holes.
*   **`physics_explosion_power.min="0.1"`, `physics_explosion_power.max="0.4"`**: The minimum and maximum force applied to physics objects within the explosion radius.
*   **`sparks_enabled="1"`**: Enables the spawning of sparks.
*   **`sparks_count_min="35"`, `sparks_count_max="50"`**: The range for the number of sparks generated.
*   **`spark_material="blood"`**: The material type of the sparks.
*   **`stains_enabled="1"`**: Enables the creation of impact stains.
*   **`stains_image="data/temp/explosion_stain.png"`**: The image used for the impact stains.
*   **`ray_energy="6000000"`**: The energy value associated with the explosion's destructive rays.
*   **`max_durability_to_destroy="12"`**: The maximum durability of objects that can be destroyed by the explosion.
*   **`audio_event_name="explosions/slime"`**: The sound event triggered by the explosion.

### Sprite Component (`<SpriteComponent>`)

Defines the visual appearance of the projectile.

*   **`image_file="data/projectiles_gfx/fireball_alt.xml"`**: The graphical asset used for the projectile.
*   **`offset_x="16"`, `offset_y="12"`**: Adjusts the positioning of the sprite relative to the projectile's origin.

### Particle Emitter Component (`<ParticleEmitterComponent>`)

Spawns cosmetic particles around the projectile.

*   **`emitted_material_name="blood"`**: The material of the particles emitted.
*   **`count_min="7"`, `count_max="15"`**: The range for the number of particles emitted per emission cycle.
*   **`lifetime_min="0.1"`, `lifetime_max="0.3"`**: The duration in seconds for which emitted particles will exist.
*   **`create_real_particles="1"`**: Indicates that these are actual game particles, not just cosmetic effects.
*   **`emission_interval_min_frames="1"`, `emission_interval_max_frames="2"`**: Controls how frequently particles are emitted.