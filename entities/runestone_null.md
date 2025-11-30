---
title: Runestone Null
category: entities
---

# Runestone Null

This document details the `runestone_null.xml` entity, representing the "Null" runestone in Noita. This runestone is primarily used for its visual effects and as a base for other runestones.

## Key Attributes

### `PhysicsImageShapeComponent`

*   **`image_file`**: `data/items_gfx/runestones/runestone_null.png`
    *   Specifies the visual sprite for the runestone when it's in the game world.

### `ItemComponent`

*   **`item_name`**: `$item_runestone_null`
    *   The internal name identifier for this item.
*   **`ui_sprite`**: `data/ui_gfx/items/runestone_null.png`
    *   The sprite used for this item in the player's inventory and UI.
*   **`ui_description`**: `$itemdesc_runestone`
    *   The description text displayed in the UI, likely referencing a generic runestone description.

### `UIInfoComponent`

*   **`name`**: `$item_runestone_null`
    *   The display name shown in the UI.

### `AbilityComponent`

*   **`ui_name`**: `$item_runestone_null`
    *   The name displayed in the UI for abilities, consistent with the item name.

### `SpriteComponent`

*   **`image_file`**: `data/items_gfx/in_hand/runestone_null.png`
    *   The sprite used when the runestone is held by the player.

### `ParticleEmitterComponent`

This component defines the visual particle effects associated with the runestone.

*   **`_tags`**: `activate`
    *   Indicates that this component is activated under certain conditions.
*   **`_enabled`**: `0`
    *   The particle emitter is disabled by default.
*   **`emitted_material_name`**: `spark_purple_bright`
    *   The type of material used for the emitted particles.
*   **`lifetime_min` / `lifetime_max`**: `8.01` / `8.1`
    *   The duration for which the particles exist.
*   **`count_min` / `count_max`**: `100` / `100`
    *   The number of particles emitted.
*   **`area_circle_radius.min` / `area_circle_radius.max`**: `16` / `16`
    *   The radius of the circular area from which particles are emitted.
*   **`velocity_always_away_from_center`**: `100`
    *   Particles are always propelled away from the emission center with a significant force.
*   **`cosmetic_force_create`**: `1`
    *   Ensures these particles are created for cosmetic purposes.

### `LuaComponent`

*   **`script_source_file`**: `data/scripts/items/runestones/runestone_null.lua`
    *   The Lua script that governs the behavior of this runestone.
*   **`execute_every_n_frame`**: `10`
    *   The script will execute its logic every 10 frames.
*   **`_tags`**: `activate`
    *   Indicates that this component is activated under certain conditions.
*   **`_enabled`**: `0`
    *   The Lua script is disabled by default.

## Summary

The `runestone_null.xml` entity defines a basic runestone with visual effects. It inherits from `runestone_base.xml` and primarily uses its `ItemComponent`, `UIInfoComponent`, and `SpriteComponent` for identification and visual representation. The `ParticleEmitterComponent` provides a distinct purple spark effect, and a `LuaComponent` points to `runestone_null.lua` for potential scripting, though both are disabled by default, suggesting it serves as a template or a placeholder.