---
title: Glue Anchor Projectile
category: entities
---

# Glue Anchor Projectile

This document details the `glue_anchor.xml` entity, which defines the behavior and properties of the Glue Anchor projectile in Noita. This projectile is used to create sticky surfaces that can impede movement and interact with other game elements.

## Core Components

The Glue Anchor projectile is built using several key components that define its visual representation, scripting, damage, and lifespan.

### SpriteComponent

This component handles the visual appearance of the Glue Anchor.

*   **`image_file`**: Specifies the graphical asset used for the projectile.
    *   `data/projectiles_gfx/glue_anchor.xml`
*   **`alpha`**: Controls the transparency of the sprite.
    *   `0.9` (slightly transparent)

### LuaComponent (Execution)

This component executes Lua scripts to manage the projectile's active behavior.

*   **`script_source_file`**: The primary script for the projectile's logic.
    *   `data/scripts/projectiles/glue_anchor.lua`
*   **`execute_every_n_frame`**: How often the script runs.
    *   `1` (every frame)

### LuaComponent (Removal)

This component executes a Lua script when the projectile is removed from the game.

*   **`script_source_file`**: The script for handling projectile removal.
    *   `data/scripts/projectiles/glue_death.lua`
*   **`execute_on_removed`**: Triggers the script upon removal.
    *   `1` (true)
*   **`execute_every_n_frame`**: Set to `-1` to indicate it only runs once on removal.

### DamageModelComponent

Defines how the projectile interacts with other entities and materials in terms of damage.

*   **`hp`**: The health of the projectile.
    *   `1`
*   **`materials_damage`**: Specifies which materials the projectile can damage.
    *   `acid,lava`
*   **`materials_how_much_damage`**: The amount of damage dealt to those materials.
    *   `0.004,0.004`
*   **`fire_probability_of_ignition`**: Chance for the projectile to ignite flammable materials.
    *   `0.8`
*   **`fire_damage_amount`**: Damage dealt by fire.
    *   `1.5`
*   **`blood_material`**: The material created when the projectile is damaged (or "dies").
    *   `glue`
*   **`blood_multiplier`**: Affects the quantity of `blood_material` created.
    *   `0.3`

### HitboxComponent

Defines the collision area of the projectile.

*   **`aabb_min_x`, `aabb_max_x`**: Defines the horizontal bounds of the bounding box.
    *   `-4`, `4`
*   **`aabb_min_y`, `aabb_max_y`**: Defines the vertical bounds of the bounding box.
    *   `-4`, `4`

### LifetimeComponent

Determines how long the projectile exists before being removed.

*   **`lifetime`**: The duration in frames.
    *   `600` (approximately 10 seconds)

### AudioComponent

Manages the sound effects associated with the projectile.

*   **`file`**: The audio bank containing the sound events.
    *   `data/audio/Desktop/projectiles.bank`
*   **`event_root`**: The base event name for projectile sounds.
    *   `projectiles/slime`

## VariableStorageComponent

This component stores variables associated with the entity.

*   **`name`**: The name of the variable.
    *   `target_1`
*   **`value_int`**: The integer value stored.
    *   `-1` (likely used as an uninitialized state or placeholder)