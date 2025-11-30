---
title: Hook Projectile
category: entities
---

# Hook Projectile

This document details the configuration of the "Hook" projectile entity in Noita, primarily focusing on its projectile behavior, visual representation, and associated effects.

## Core Components

The Hook projectile is defined by several key components that dictate its functionality:

### Base Projectile (`BaseComponent`)

Inherits fundamental projectile properties.

*   **`gravity_y`**: `120` - Controls the downward acceleration due to gravity.
*   **`air_friction`**: `1.2` - Affects how air resistance slows the projectile.
*   **`mass`**: `0.07` - The projectile's mass, influencing its interaction with physics.

### Projectile Behavior (`ProjectileComponent`)

This is the primary component defining the projectile's unique characteristics.

*   **`lob_min` / `lob_max`**: `0.5` / `0.7` - Defines the minimum and maximum lob angle (deviation from straight trajectory).
*   **`speed_min` / `speed_max`**: `680` / `720` - Sets the range for the projectile's initial speed.
*   **`friction`**: `0.8` - Additional friction applied to the projectile.
*   **`on_death_explode`**: `1` - The projectile will explode upon death.
*   **`on_lifetime_out_explode`**: `1` - The projectile will explode when its lifetime expires.
*   **`on_collision_die`**: `1` - The projectile will be destroyed upon collision.
*   **`lifetime`**: `60` - The base duration (in frames) the projectile exists before expiring.
*   **`lifetime_randomness`**: `7` - Adds randomness to the projectile's lifetime.
*   **`damage`**: `0.30` - The base damage dealt by the projectile.
*   **`knockback_force`**: `1.8` - The force applied to knock back entities upon impact.
*   **`physics_impulse_coeff`**: `1500` - Coefficient for physics impulse calculations.

#### Explosion Configuration (`config_explosion`)

Defines the properties of the explosion when the projectile detonates.

*   **`damage`**: `0` - The explosion itself does not deal direct damage.
*   **`camera_shake`**: `0.5` - The intensity of camera shake caused by the explosion.
*   **`explosion_radius`**: `2` - The radius of the explosion effect.
*   **`explosion_sprite`**: `data/particles/explosion_016_slime.xml` - The visual sprite used for the explosion.
*   **`hole_enabled`**: `1` - The explosion can create holes in terrain.
*   **`ray_energy`**: `400000` - Energy value for raycasting effects related to the explosion.
*   **`physics_explosion_power.min` / `.max`**: `0.02` / `0.1` - The range of physics force applied by the explosion.
*   **`shake_vegetation`**: `1` - The explosion will shake vegetation.
*   **`light_enabled`**: `1` - The explosion emits light.
*   **`light_r` / `g` / `b`**: `40` / `90` / `10` - The color of the explosion's light.
*   **`stains_enabled`**: `1` - The explosion leaves stains.

### Visual Representation (`SpriteComponent`)

Determines how the projectile appears in-game.

*   **`image_file`**: `data/projectiles_gfx/hook.xml` - Specifies the sprite sheet or animation file.
*   **`additive`**: `1` - Enables additive blending for the sprite, often used for glowing effects.

### Particle Emitter (`ParticleEmitterComponent`)

Manages the emission of cosmetic particles.

*   **`emitted_material_name`**: `spark_green` - The type of material used for the emitted sparks.
*   **`is_trail`**: `1` - The particles are emitted as a trail behind the projectile.
*   **`render_on_grid`**: `1` - Particles are rendered on the game grid.
*   **`fade_based_on_lifetime`**: `1` - Particles fade out as their lifetime decreases.

### Audio (`AudioComponent`)

Handles sound effects associated with the projectile.

*   **`file`**: `data/audio/Desktop/projectiles.bank` - The audio bank containing the sound events.
*   **`event_root`**: `player_projectiles/bullet` - The root event path for player projectile sounds.

### Light (`LightComponent`)

Defines the light emitted by the projectile.

*   **`radius`**: `40` - The radius of the light source.
*   **`r` / `g` / `b`**: `40` / `120` / `10` - The color of the emitted light.

### Lua Script (`LuaComponent`)

Attaches custom Lua scripting for advanced behavior.

*   **`script_source_file`**: `data/scripts/projectiles/hook.lua` - The path to the Lua script file.
*   **`execute_on_removed`**: `1` - The script will execute when the entity is removed.
*   **`execute_every_n_frame`**: `999999` - This value suggests the script might be intended for specific trigger conditions rather than continuous execution.

---