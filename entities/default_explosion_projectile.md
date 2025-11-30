---
title: Default Explosion Projectile
category: entities
---

# Default Explosion Projectile

This document details the configuration of the default explosion projectile entity in Noita, primarily focusing on its behavior and visual aspects when it detonates.

## Entity Definition

The core of this entity is based on `data/entities/base_projectile.xml`, inheriting its fundamental projectile properties.

```xml
<Entity
  name="$projectile_default"
>
  <Base file="data/entities/base_projectile.xml">
    <VelocityComponent
      gravity_y="100"
    >
    </VelocityComponent>
  </Base>
  </Entity>
```

## Projectile Component

This component defines the projectile's movement, detonation conditions, and the specifics of the explosion it creates.

### Key Attributes:

*   **`lob_min`, `lob_max`**: Controls the arc of the projectile's trajectory.
*   **`speed_min`, `speed_max`**: Sets the initial velocity range.
*   **`on_death_explode`**: When set to `1`, the projectile explodes upon death.
*   **`on_lifetime_out_explode`**: Triggers an explosion when the projectile's lifetime expires.
*   **`explosion_dont_damage_shooter`**: If `1`, prevents the explosion from harming the entity that fired it.
*   **`die_on_low_velocity`**: Causes the projectile to die (and potentially explode) if its velocity drops too low.
*   **`damage`**: Base damage of the projectile itself (before explosion).
*   **`on_collision_die`**: If `1`, the projectile dies upon colliding with something.
*   **`lifetime`**: The duration in seconds before the projectile expires (and potentially explodes).

### Explosion Configuration (`config_explosion`):

This nested element defines the parameters of the explosion itself.

*   **`camera_shake`**: The intensity of camera shake caused by the explosion.
*   **`damage`**: The damage dealt by the explosion.
*   **`explosion_radius`**: The area of effect for the explosion.
*   **`explosion_sprite`**: The visual effect used for the explosion (e.g., a particle effect).
*   **`create_cell_probability`**: The chance (in percent) of creating a material cell at the explosion site.
*   **`create_cell_material`**: The material of the cell to be created (e.g., "fire").
*   **`hole_enabled`**: If `1`, the explosion creates a hole in the environment.
*   **`hole_image`**: The texture used for the explosion hole.
*   **`particle_effect`**: If `1`, enables particle effects associated with the explosion.
*   **`physics_explosion_power.min`, `physics_explosion_power.max`**: The minimum and maximum force applied to physics objects within the explosion radius.
*   **`physics_throw_enabled`**: If `1`, physics objects are thrown by the explosion.
*   **`shake_vegetation`**: If `1`, causes vegetation to shake.
*   **`sparks_count_min`, `sparks_count_max`**: The range for the number of sparks generated.
*   **`sparks_enabled`**: If `1`, sparks are generated.
*   **`stains_enabled`**: If `1`, explosion stains are left on surfaces.
*   **`stains_image`**: The texture used for explosion stains.
*   **`ray_energy`**: The energy value associated with the explosion for ray interactions.

```xml
  <ProjectileComponent
    _enabled="1"
    lob_min="0.8"
    lob_max="1.0"
    speed_min="160"
    speed_max="170"
    on_death_explode="1"
    on_death_gfx_leave_sprite="0"
    on_lifetime_out_explode="1"
    explosion_dont_damage_shooter="0"
    die_on_low_velocity="1"
    damage="0"
    on_collision_die="1"
    lifetime="1" >
    <config_explosion
      never_cache="0"
      camera_shake="13"
      damage="5"
      explosion_radius="25"
      explosion_sprite="data/particles/explosion_040_poof.xml"
      explosion_sprite_lifetime="0"
      explosion_sprite_random_rotation="0"
      create_cell_probability="20"
      create_cell_material="fire"
      hole_destroy_liquid="0"
      hole_enabled="1"
      hole_image="data/temp/explosion_hole.png"
      particle_effect="1"
      physics_explosion_power.min="1.0"
      physics_explosion_power.max="1.7"
      physics_throw_enabled="1"
      shake_vegetation="1"
      sparks_count_min="7"
      sparks_count_max="14"
      sparks_enabled="1"
      stains_enabled="1"
      stains_image="data/temp/explosion_stain.png"
      ray_energy="20000">
    </config_explosion>
  </ProjectileComponent>
```

## Sprite Component

This component defines the visual representation of the projectile itself before it explodes.

*   **`image_file`**: The path to the sprite's image file.
*   **`offset_x`, `offset_y`**: Adjusts the sprite's position relative to the entity's origin.

```xml
  <SpriteComponent
    _enabled="1"
    alpha="1"
    image_file="data/projectiles_gfx/fireball_alt.xml"
    offset_x="16"
    offset_y="12"
  >
  </SpriteComponent>
```

## Variable Storage Component

This component stores a variable that can be referenced by other parts of the game, in this case, the projectile's own file path.

*   **`name`**: The name of the variable.
*   **`value_string`**: The string value assigned to the variable.

```xml
  <VariableStorageComponent
    name="projectile_file"
    value_string="data/entities/projectiles/explosion.xml"
  >
  </VariableStorageComponent>
```