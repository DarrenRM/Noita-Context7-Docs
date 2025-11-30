---
title: Firepillar Part Projectile
category: entities
---

# Firepillar Part Projectile

This entity defines a projectile used by the boss centipede, specifically its "firepillar" attack. It's a projectile that explodes on impact or when its lifetime expires, leaving behind fire particles and a light source.

## Key Components

### Base Projectile (`<Base file="data/entities/base_projectile.xml">`)

This component inherits fundamental projectile properties.

*   **`gravity_y`**: `250` - Applies a downward gravitational pull.
*   **`air_friction`**: `0` - No air resistance.
*   **`mass`**: `0.05` - Low mass for the projectile.

### Projectile Behavior (`<ProjectileComponent>`)

Defines the core mechanics of the projectile.

*   **`lob_min` / `lob_max`**: `0.8` / `1.0` - Controls the arc of the projectile.
*   **`speed_min` / `speed_max`**: `350` - Sets a fixed projectile speed.
*   **`die_on_low_velocity`**: `0` - The projectile does not die if its velocity drops too low.
*   **`on_death_explode`**: `1` - The projectile explodes when it dies.
*   **`on_lifetime_out_explode`**: `1` - The projectile explodes when its lifetime ends.
*   **`explosion_dont_damage_shooter`**: `1` - The explosion will not harm the entity that fired it.
*   **`damage`**: `0` - This projectile itself does not deal direct damage. Damage is handled by the explosion.
*   **`on_collision_die`**: `1` - The projectile dies upon colliding with something.
*   **`lifetime`**: `300` - The projectile exists for 300 frames before expiring.
*   **`knockback_force`**: `1.0` - Applies a knockback effect on collision.

#### Damage by Type (`<damage_by_type>`)

*   **`fire`**: `0.8` - The explosion deals 0.8 damage of type "fire".

#### Explosion Configuration (`<config_explosion>`)

Details the explosion effect.

*   **`never_cache`**: `1` - Prevents caching of this explosion for performance.
*   **`camera_shake`**: `0` - No camera shake on explosion.
*   **`explosion_radius`**: `6` - The radius of the explosion.
*   **`explosion_sprite`**: `data/particles/explosion_016.xml` - The visual effect for the explosion.
*   **`ray_energy`**: `5000` - The energy of the explosion's damaging rays.
*   **`hole_destroy_liquid`**: `1` - The explosion can destroy liquids.
*   **`hole_enabled`**: `1` - Creates a hole in terrain.
*   **`hole_image`**: `data/temp/explosion_hole.png` - The image used for the hole.
*   **`physics_explosion_power.min` / `.max`**: `0.3` / `0.4` - The minimum and maximum force of the physics-based explosion.
*   **`physics_throw_enabled`**: `1` - Objects affected by the explosion can be thrown.
*   **`shake_vegetation`**: `1` - Vegetation is affected by the explosion.
*   **`light_r` / `g` / `b`**: `60` / `140` / `30` - The color of the light emitted by the explosion.

### Particle Emitters

#### Fire Particle Emitter (`<ParticleEmitterComponent>`)

Generates trailing fire particles.

*   **`emitted_material_name`**: `fire` - The material of the particles.
*   **`gravity.y`**: `0.10` - Slight downward gravity for particles.
*   **`count_min` / `count_max`**: `5` / `34` - Number of particles emitted per burst.
*   **`lifetime_min` / `lifetime_max`**: `0.6` / `0.8` - Duration of each particle.
*   **`is_trail`**: `1` - Particles form a trail.
*   **`airflow_force`**: `1.1` - Influences particle movement with airflow.

#### Spark Particle Emitter (`<ParticleEmitterComponent>`)

Generates sparks on emission.

*   **`_tags`**: `enabled_in_world,enabled_in_hand,fire` - Activation conditions.
*   **`emitted_material_name`**: `spark` - The material of the particles.
*   **`custom_style`**: `FIRE` - Applies a specific style to the sparks.
*   **`y_vel_min` / `y_vel_max`**: `-20` / `-10` - Upward initial velocity for sparks.
*   **`count_min` / `count_max`**: `4` / `6` - Number of sparks emitted.
*   **`lifetime_min` / `lifetime_max`**: `0.3` / `0.4` - Duration of each spark.

### Visuals

#### Sprite Component (`<SpriteComponent>`)

Defines the visual appearance of the projectile.

*   **`image_file`**: `data/projectiles_gfx/grenade_large.xml` - The sprite asset used.
*   **`rect_animation`**: `spawn` - Specifies the animation to play.

#### Light Component (`<LightComponent>`)

Adds a light source to the projectile.

*   **`radius`**: `150` - The radius of the light.
*   **`r` / `g` / `b`**: `180` / `140` / `30` - The color of the light (orange/yellow).

### Variables

#### Projectile File Variable (`<VariableStorageComponent>`)

Stores the path to this entity's XML file.

*   **`name`**: `projectile_file`
*   **`value_string`**: `data/entities/animals/boss_centipede/firepillar_part.xml`