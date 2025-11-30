---
title: Lava Orb Projectile
category: entities
---

# Lava Orb Projectile

This document describes the `orb_mat_lava.xml` entity, which represents a projectile fired by the boss centipede that explodes into lava.

## Entity Definition

The core entity is a projectile with the tag `hittable`.

```xml
<Entity tags="hittable"
  name="$projectile_default"
>
  <!-- ... components ... -->
</Entity>
```

## Key Components

### Base Projectile (`BaseComponent`)

This component defines the fundamental projectile properties.

*   **`gravity_y="0"`**: The projectile is not affected by gravity.
*   **`air_friction="1"`**: High air friction, suggesting it might slow down quickly if not propelled.
*   **`mass="0.05"`**: A very small mass.

### Projectile Behavior (`ProjectileComponent`)

This component governs the projectile's movement, lifespan, and death behavior.

*   **`lob_min="0.8"`, `lob_max="1.0"`**: Controls the lobbing behavior, with a high minimum, suggesting a relatively straight trajectory.
*   **`speed_min="40"`, `speed_max="60"`**: Defines the projectile's initial speed range.
*   **`die_on_low_velocity="0"`**: The projectile does not die simply due to low velocity.
*   **`on_death_explode="1"`**: The projectile explodes upon death.
*   **`on_lifetime_out_explode="1"`**: The projectile explodes when its lifetime expires.
*   **`damage="0"`**: The projectile itself does not deal direct damage.
*   **`lifetime="400"`**: The projectile exists for 400 frames before expiring.
*   **`knockback_force="1.0"`**: Applies a knockback force upon collision.

#### Explosion Configuration (`config_explosion`)

This nested element details the explosion properties.

*   **`never_cache="1"`**: Prevents caching of this explosion.
*   **`camera_shake="0"`**: No camera shake is applied.
*   **`explosion_radius="16"`**: The radius of the explosion.
*   **`explosion_sprite="data/particles/explosion_016_plasma_pink.xml"`**: The visual effect of the explosion.
*   **`create_cell_probability="100"`**: Always creates cells upon explosion.
*   **`create_cell_material="lava"`**: The created cells are of the "lava" material.
*   **`ray_energy="5000"`**: High energy for ray interactions.
*   **`hole_destroy_liquid="1"`**: The explosion destroys liquids.
*   **`hole_enabled="1"`**: Creates holes in surfaces.
*   **`hole_image="data/temp/explosion_hole.png"`**: The image used for the hole.
*   **`physics_explosion_power.min="0.13"`, `physics_explosion_power.max="0.23"`**: The force of the physics-based explosion.
*   **`light_r="15"`, `light_g="15"`, `light_b="40"`**: Defines the color of the light emitted by the explosion.

### Particle Emitter (`ParticleEmitterComponent`)

This component generates cosmetic particles.

*   **`emitted_material_name="spark"`**: Emits particles of the "spark" material.
*   **`lifetime_min="3.5"`, `lifetime_max="7.5"`**: The lifespan of emitted particles.
*   **`count_min="2"`, `count_max="4"`**: The number of particles emitted per emission.
*   **`area_circle_radius.max="10"`**: The radius of the emission area.
*   **`cosmetic_force_create="0"`**: Particles are not created with cosmetic force.

### Sprite (`SpriteComponent`)

Defines the visual appearance of the projectile.

*   **`image_file="data/entities/animals/boss_centipede/orb_mat_lava_gfx.xml"`**: The sprite file used for the projectile.
*   **`rect_animation="spawn"`**: Uses the "spawn" animation.

### Light (`LightComponent`)

Adds a light source to the projectile.

*   **`radius="150"`**: The radius of the light.
*   **`r="130"`, `g="35"`, `b="90"`**: The color of the light (a reddish-purple hue).

### Audio (`AudioComponent`)

Handles sound effects for the projectile.

*   **`file="data/audio/Desktop/projectiles.bank"`**: The audio bank file.
*   **`event_root="projectiles/magic"`**: The root event for projectile sounds.

### Lua Script (`LuaComponent`)

Attaches a Lua script for custom behavior.

*   **`script_source_file="data/entities/animals/boss_centipede/orb_mat_animate.lua"`**: The Lua script file.
*   **`remove_after_executed="1"`**: The script is removed after execution.
*   **`execute_every_n_frame="300"`**: The script executes every 300 frames.

### Hitbox (`HitboxComponent`)

Defines the collision area of the projectile.

*   **`aabb_min_x="-9"`, `aabb_max_x="9"`**: The X-axis bounds of the hitbox.
*   **`aabb_min_y="-9"`, `aabb_max_y="9"`**: The Y-axis bounds of the hitbox.

### Damage Model (`DamageModelComponent`)

Specifies how the projectile interacts with damage and materials.

*   **`hp="0.6"`**: The projectile has very low health.
*   **`blood_material="lava"`**: When damaged, it leaves "lava" material.
*   **`blood_multiplier="0"`**: No multiplier for blood effects.

### Variable Storage (`VariableStorageComponent`)

Stores custom variables for the entity.

*   **`name="projectile_file"`**: The name of the variable.
*   **`value_string="data/entities/animals/boss_centipede/orb_mat_lava.xml"`**: Stores the entity's own file path.