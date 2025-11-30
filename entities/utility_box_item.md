---
title: Utility Box Item
category: entities
---

---

# Utility Box Item

This document describes the `utility_box.xml` entity, which represents a utility box item in Noita. This item is designed to be picked up and has associated visual and functional components.

## Core Components

The `utility_box.xml` entity is defined by several key components that dictate its behavior and appearance:

### UIInfoComponent

This component provides basic information for the item's UI representation.

*   **`name`**: `$item_utility_box` - The internal name used for UI display.

### PhysicsBodyComponent

Defines the physical properties of the utility box in the game world.

*   **`uid`**: `1` - Unique identifier for this physics body.
*   **`allow_sleep`**: `1` - Allows the physics body to enter a sleep state when inactive.
*   **`auto_clean`**: `1` - Automatically cleans up the physics body when no longer needed.
*   **`hax_fix_going_through_ground`**: `1` - A fix to prevent the object from falling through the ground.

### PhysicsImageShapeComponent

Determines the visual shape and material of the utility box based on an image.

*   **`body_id`**: `1` - Links this shape to the `PhysicsBodyComponent` with `uid="1"`.
*   **`image_file`**: `data/items_gfx/utility_box.png` - The sprite used for the utility box.
*   **`material`**: `metal_prop` - The physical material properties.

### ItemComponent

Defines the item's properties when it's an inventory item.

*   **`item_name`**: `$item_utility_box` - The internal name of the item.
*   **`stats_count_as_item_pick_up`**: `0` - This item does not count towards general item pickup statistics.
*   **`custom_pickup_string`**: `$itempickup_open` - The string displayed when the player interacts with it for pickup.
*   **`play_pick_sound`**: `0` - No specific sound is played upon pickup.

### LuaComponent (Scripting)

These components attach Lua scripts to the entity, defining its interactive behavior.

*   **`script_physics_body_modified`**: `data/scripts/items/utility_box.lua`
    *   **`execute_times`**: `1` - This script is executed only once when the physics body is modified.
*   **`script_item_picked_up`**: `data/scripts/items/utility_box.lua`
    *   This script is executed when the item is picked up by the player.

### LightComponent

Adds a light source to the utility box.

*   **`r`, `g`, `b`**: `255`, `255`, `255` - Sets the light color to white.
*   **`radius`**: `64` - The radius of the light emitted.
*   **`fade_out_time`**: `0.75` - The time it takes for the light to fade out.