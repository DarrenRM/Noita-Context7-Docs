---
title: Sentry Shot Projectile
category: entities
---

# Sentry Shot Projectile

This document details the configuration of the `sentryshot.xml` entity, which defines the behavior and appearance of a projectile fired by sentries in Noita.

## Core Components

### Base Projectile (`BaseComponent`)

This component inherits fundamental projectile properties.

*   **`gravity_y`**: `0` - The projectile is not affected by gravity.
*   **`air_friction`**: `-2` - A slight negative air friction, potentially affecting its trajectory subtly.
*   **`mass`**: `0.05` - A very low mass, contributing to its speed and responsiveness.

### Homing Behavior (`HomingComponent`)

This component enables the projectile to track its target.

*   **`homing_targeting_coeff`**: `20.0` - A high coefficient indicates strong homing capabilities.
*   **`homing_velocity_multiplier`**: `0.99` - The projectile slightly reduces its speed when actively homing.
*   **`detect_distance`**: `60` - The range within which the projectile can detect and target enemies.

### Projectile Properties (`ProjectileComponent`)

This is the primary component defining the projectile's direct behavior.

*   **`lob_min` / `lob_max`**: `0.8` / `1.0` - Controls the arc of the projectile, suggesting a relatively straight trajectory.
*   **`speed_min` / `speed_max`**: `350` - The projectile travels at a constant, high speed.
*   **`damage`**: `0` - This projectile itself deals no direct damage.
*   **`lifetime`**: `100` - The projectile exists for a duration of 100 frames.
*   **`knockback_force`**: `1.0` - Applies a small knockback effect upon collision.
*   **`on_collision_die`**: `1` - The projectile is destroyed upon hitting a surface or entity.
*   **`muzzle_flash_file`**: `data/entities/particles/muzzle_flashes/muzzle_flash_magic_launcher_blue.xml` - Specifies the visual effect at the point of origin.
*   **`shoot_light_flash_r/g/b/radius`**: `50/125/235/100` - Defines the color and radius of a light flash emitted when the projectile is fired.

### Sprite (`SpriteComponent`)

Defines the visual representation of the projectile.

*   **`image_file`**: `data/projectiles_gfx/target.xml` - The texture used for the projectile.
*   **`rect_animation`**: `fireball` - Specifies an animation sequence from the image file.
*   **`additive`**: `1` - Enables additive blending for a glowing effect.
*   **`emissive`**: `1` - The sprite emits light.

### Audio (`AudioComponent`)

Handles sound effects associated with the projectile.

*   **`file`**: `data/audio/Desktop/projectiles.bank` - The audio bank containing the sound events.
*   **`event_root`**: `projectiles/laser` - The specific sound event for this projectile.

### Particle Emitters (`ParticleEmitterComponent`)

Two emitters are used to create visual effects.

**Emitter 1 (Trail Sparks):**
*   **`emitted_material_name`**: `spark_blue` - The material for the emitted particles.
*   **`is_trail`**: `1` - Creates a trailing effect.
*   **`lifetime_min/max`**: `0.1/0.2` - Short lifespan for these particles.
*   **`count_min/max`**: `1/1` - Emits a single particle per emission.

**Emitter 2 (Plasma Fading):**
*   **`emitted_material_name`**: `plasma_fading` - The material for these particles.
*   **`is_trail`**: `1` - Creates a trailing effect.
*   **`lifetime_min/max`**: `0.2/0.6` - Longer lifespan for these particles.
*   **`x_vel_min/max`**: `20/80` - Particles are ejected with significant horizontal velocity.

### Light (`LightComponent`)

Adds a dynamic light source to the projectile.

*   **`radius`**: `150` - The radius of the light emitted.
*   **`r/g/b`**: `30/90/30` - The color of the light (a greenish-blue hue).

### Hit Effect (`HitEffectComponent`)

Determines what happens when the projectile collides with something.

*   **`effect_hit`**: `LOAD_CHILD_ENTITY` - Loads another entity upon impact.
*   **`value_string`**: `data/entities/misc/sentry_target.xml` - The entity to load, likely a visual or functional effect for the target.