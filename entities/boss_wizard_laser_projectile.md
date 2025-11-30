---
title: Boss Wizard Laser Projectile
category: entities
---

# Boss Wizard Laser Projectile

This document details the configuration for the Boss Wizard's laser projectile in Noita, intended for AI-assisted modding.

## Entity Definition

The core entity definition for the boss wizard's laser projectile.

```xml
<Entity
  name="$projectile_default"
  tags="boss_wizard_laser"
>
  <!-- ... components ... -->
</Entity>
```

## Key Components

### Base Projectile (`BaseComponent`)

Inherits fundamental projectile properties.

*   **`gravity_y="0"`**: The projectile is not affected by gravity.
*   **`air_friction="2"`**: Moderate air resistance.
*   **`mass="0.8"`**: Relatively light projectile.

### Projectile Behavior (`ProjectileComponent`)

Defines the projectile's movement, lifespan, and death effects.

*   **`lob_min="0.8"`, `lob_max="1.0"`**: Controls the projectile's arc, with minimal to no lobbing.
*   **`speed_min="100"`, `speed_max="120"`**: Sets the projectile's initial velocity range.
*   **`die_on_low_velocity="0"`**: The projectile does not die solely due to low speed.
*   **`on_death_explode="1"`**: The projectile explodes upon death.
*   **`on_lifetime_out_explode="1"`**: The projectile explodes when its lifetime expires.
*   **`explosion_dont_damage_shooter="1"`**: The explosion does not harm the entity that fired it.
*   **`damage="1.8"`**: Base damage dealt by the projectile itself.
*   **`on_collision_die="1"`**: The projectile dies upon colliding with something.
*   **`lifetime="100"`**: The projectile exists for 100 frames before expiring.
*   **`knockback_force="2.0"`**: Applies a knockback effect upon collision or explosion.
*   **`velocity_sets_scale="1"`**: Velocity influences the scale of certain effects.

#### Explosion Configuration (`config_explosion`)

Details the effects of the projectile's explosion.

*   **`never_cache="1"`**: Prevents caching of this explosion for performance.
*   **`camera_shake="4.0"`**: Significant camera shake upon explosion.
*   **`explosion_radius="20"`**: The radius of the explosion.
*   **`explosion_sprite="data/particles/explosion_032_plasma.xml"`**: The visual effect for the explosion.
*   **`create_cell_probability="1"`**: Always creates a cell upon explosion.
*   **`create_cell_material="plasma_fading"`**: The material of the created cell.
*   **`ray_energy="10000"`**: High energy for potential ray interactions.
*   **`hole_destroy_liquid="1"`**: The explosion can destroy liquids.
*   **`hole_enabled="1"`**: Creates a hole in terrain.
*   **`damage="3.5"`**: Damage dealt by the explosion.
*   **`hole_image="data/temp/explosion_hole.png"`**: The image used for the terrain hole.
*   **`physics_explosion_power.min="0.4"`, `physics_explosion_power.max="0.6"`**: Controls the physics force of the explosion.
*   **`physics_throw_enabled="1"`**: Objects can be thrown by the explosion.
*   **`shake_vegetation="1"`**: Vegetation is shaken by the explosion.
*   **`sparks_enabled="1"`**: Sparks are generated.
*   **`spark_material="plasma_fading"`**: The material of the sparks.
*   **`sparks_count_min="12"`, `sparks_count_max="16"`**: Number of sparks generated.
*   **`light_r="25"`, `light_g="95"`, `light_b="190"`**: Blueish light emitted by the explosion.

### Lua Scripting (`LuaComponent`)

Custom logic applied to the projectile.

*   **`script_source_file="data/scripts/projectiles/phasing_arc.lua"`**: Applies phasing arc behavior, executed every 12 frames.
*   **`script_source_file="data/entities/animals/boss_wizard/laser.lua"`**: Additional boss laser specific logic, executed every 60 frames.

### Visuals (`SpriteComponent`)

Defines the projectile's appearance.

*   **`image_file="data/projectiles_gfx/orb_blue_big.xml"`**: Uses a large blue orb graphic.
*   **`rect_animation="fireball"`**: Specifies the animation to use.
*   **`offset_x="8"`, `offset_y="8"`**: Offsets the sprite's position.
*   **`additive="1"`**: Uses additive blending for a glowing effect.

### Lighting (`LightComponent`)

Emits light.

*   **`radius="150"`**: The radius of the light.
*   **`r="10"`, `g="85"`, `b="190"`**: Blueish light color.

### Audio (`AudioComponent`)

Sound effects associated with the projectile.

*   **`file="data/audio/Desktop/projectiles.bank"`**: The audio bank file.
*   **`event_root="projectiles/orb_b"`**: The root event for orb sounds.

### Variable Storage (`VariableStorageComponent`)

Stores custom variables.

*   **`name="projectile_file"`**: Stores the path to this entity's XML file.
*   **`value_string="data/entities/animals/boss_wizard/laser.xml"`**: The value of the variable.