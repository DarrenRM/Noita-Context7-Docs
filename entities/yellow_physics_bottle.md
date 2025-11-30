---
title: Yellow Physics Bottle
category: entities
---

# Yellow Physics Bottle

This document describes the `physics_bottle_yellow.xml` entity, which represents a breakable yellow bottle filled with molten gold.

## Base Entity

The entity inherits its core functionality from `base_item_physics2.xml`.

### Key Components:

*   **`PhysicsBody2Component`**:
    *   `kill_entity_after_initialized`: Set to `0`, meaning the entity persists after its initial setup.
*   **`PhysicsImageShapeComponent`**:
    *   `image_file`: Specifies the visual asset for the bottle (`data/props_gfx/bottle_yellow.png`).
    *   `material`: Defines the physical material of the bottle's shape (`plastic_prop`).

## Material Inventory

This component manages the contents of the bottle.

### Key Attributes:

*   **`_enabled`**: Set to `1`, meaning the component is active.
*   **`drop_as_item`**: Set to `0`, indicating the contents do not drop as a separate item upon breaking.
*   **`on_death_spill`**: Set to `1`, meaning the contents will spill when the entity is destroyed.
*   **`leak_on_damage_percent`**: Set to `0.999`, meaning the bottle will leak its contents when it reaches 99.9% damage.

### `count_per_material_type`

This table defines the materials and their quantities contained within the bottle.

| Material      | Count |
| :------------ | :---- |
| `gold_molten` | 100   |

## Damage Model

This component handles how the entity takes damage and its reactions.

### Key Attributes:

*   **`air_needed`**: Set to `0`, meaning air is not required for its damage mechanics.
*   **`blood_material`**: Set to `gold_molten`, indicating molten gold is the material associated with damage events.
*   **`drop_items_on_death`**: Set to `0`, so no items are dropped when it dies.
*   **`falling_damage_damage_max`**: Maximum damage from falling (`1.2`).
*   **`falling_damage_damage_min`**: Minimum damage from falling (`0.1`).
*   **`falling_damage_height_max`**: Maximum height for falling damage calculation (`250`).
*   **`falling_damage_height_min`**: Minimum height for falling damage calculation (`70`).
*   **`falling_damages`**: Set to `1`, enabling falling damage.
*   **`fire_damage_amount`**: Amount of damage from fire (`0.2`).
*   **`fire_probability_of_ignition`**: Probability of igniting from fire (`50`).
*   **`critical_damage_resistance`**: Resistance to critical damage (`1`).
*   **`hp`**: Hit points of the bottle (`0.1`).
*   **`is_on_fire`**: Set to `0`, the bottle is not initially on fire.
*   **`materials_create_messages`**: Set to `0`, no messages are created when materials interact.
*   **`materials_damage`**: Set to `0`, materials do not directly cause damage to the bottle.
*   **`ui_report_damage`**: Set to `0`, damage is not reported in the UI.

## Explode on Damage

This component defines the explosion behavior when the entity takes damage.

### Key Attributes:

*   **`explode_on_death_percent`**: Set to `1`, the entity will explode upon death.
*   **`explode_on_damage_percent`**: Set to `0.8`, the entity will explode when it reaches 80% damage.
*   **`physics_body_modified_death_probability`**: Probability of physics body modification on death (`0.1`).

### `config_explosion`

Configuration for the explosion effect.

| Attribute                     | Value                               | Description                                     |
| :---------------------------- | :---------------------------------- | :---------------------------------------------- |
| `never_cache`                 | `0`                                 | Caching is enabled.                             |
| `damage`                      | `1`                                 | Base damage of the explosion.                   |
| `camera_shake`                | `12`                                | Intensity of camera shake.                      |
| `explosion_radius`            | `5`                                 | Radius of the explosion.                        |
| `explosion_sprite`            | `data/particles/explosion_032.xml`  | Visual effect for the explosion.                |
| `explosion_sprite_lifetime`   | `10`                                | Lifetime of the explosion sprite.               |
| `create_cell_probability`     | `0`                                 | Probability of creating cells.                  |
| `create_cell_material`        | `fire`                              | Material of created cells (if any).             |
| `hole_destroy_liquid`         | `0`                                 | Holes do not destroy liquids.                   |
| `hole_enabled`                | `1`                                 | Hole creation is enabled.                       |
| `ray_energy`                  | `180000`                            | Energy of the explosion's rays.                 |
| `particle_effect`             | `1`                                 | Particle effects are enabled.                   |
| `damage_mortals`              | `1`                                 | Explosion damages mortals.                      |
| `physics_explosion_power.min` | `0.32`                              | Minimum physics force of the explosion.         |
| `physics_explosion_power.max` | `0.44`                              | Maximum physics force of the explosion.         |
| `physics_throw_enabled`       | `1`                                 | Physics objects are thrown by the explosion.    |
| `shake_vegetation`            | `1`                                 | Vegetation is shaken by the explosion.          |
| `sparks_count_min`            | `0`                                 | Minimum number of sparks.                       |
| `sparks_count_max`            | `0`                                 | Maximum number of sparks.                       |
| `sparks_enabled`              | `0`                                 | Sparks are disabled.                            |
| `stains_enabled`              | `1`                                 | Stains are enabled.                             |
| `stains_radius`               | `15`                                | Radius of the stains.                           |