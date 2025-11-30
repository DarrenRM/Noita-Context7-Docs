---
title: Statue Entity
category: entities
---

# Statue Entity

This document describes the `statue.xml` entity, a basic building element in Noita. It's designed to be a static, hittable object with minimal interactive components.

## Core Components

The statue entity is primarily defined by its visual representation, hitbox, and how it reacts to damage and materials.

### `DamageModelComponent`

This component governs how the statue handles damage and its overall durability.

*   **`hp`**: The statue has very low health, set to `0.2`.
*   **`max_hp`**: Matches `hp`, indicating it cannot be healed beyond its initial value.
*   **`critical_damage_resistance`**: Set to `1`, meaning it takes full damage from critical hits.
*   **`materials_damage`**: Set to `1`, allowing materials to damage it.
*   **`materials_how_much_damage`**: Materials inflict `0.1` damage.
*   **`drop_items_on_death`**: Set to `0`, so it doesn't drop items when destroyed.
*   **`falling_damages`**: Set to `0`, it is unaffected by fall damage.

### `HitboxComponent`

Defines the physical boundaries of the statue.

*   **`aabb_max_x`**: `4.5`
*   **`aabb_max_y`**: `0`
*   **`aabb_min_x`**: `-4.5`
*   **`aabb_min_y`**: `-16`
*   **`is_enemy`**, **`is_item`**, **`is_player`**: All set to `0`, indicating it's neither an enemy, item, nor player.

### `SpriteComponent`

Determines the visual appearance of the statue.

*   **`image_file`**: `data/buildings_gfx/statue.xml` - This points to the graphical assets for the statue.
*   **`alpha`**: `1` (fully opaque).
*   **`offset_x`**, **`offset_y`**: `0`, meaning no positional offset for the sprite.

### `MaterialInventoryComponent`

This component defines the materials contained within the statue and how they behave when the statue is damaged or destroyed.

*   **`on_death_spill`**: Set to `1`, meaning its contents will spill out upon destruction.
*   **`leak_on_damage_percent`**: Set to `0.999`, indicating it will only leak its contents when almost completely destroyed.
*   **`count_per_material_type`**:
    *   **`Material material="sand" count="50"`**: The statue contains 50 units of sand.

## Other Components

*   **`SimplePhysicsComponent`**: Provides basic physics properties.
*   **`VelocityComponent`**: Allows for velocity to be applied.