---
title: Aggressive Potion Item
category: entities
---

# Aggressive Potion Item

This document describes the `potion_aggressive.xml` entity, which defines an aggressive potion pickup item in Noita.

## Key Attributes

This item inherits its base properties from `data/entities/items/pickup/potion.xml`.

### Entity Tags

*   `projectile_item`: Indicates that this entity can be thrown or fired as a projectile.

### Components

*   **`PhysicsImageShapeComponent`**:
    *   `image_file`: `data/items_gfx/potion_alchemist_normals.png` - Specifies the normal map texture for the physics shape.

*   **`SpriteComponent`**:
    *   `image_file`: `data/items_gfx/potion_alchemist.png` - The primary visual sprite for the potion.
    *   `offset_x`: `4` - Horizontal offset for the sprite.
    *   `offset_y`: `4` - Vertical offset for the sprite.

*   **`ItemComponent`**:
    *   `item_name`: `$item_potion` - The internal name for the item.
    *   `ui_sprite`: `data/ui_gfx/items/potion_alchemist.png` - The sprite used in the UI.
    *   `ui_description`: `$item_description_potion` - The description text for the item in the UI.

*   **`LuaComponent` (Script Execution)**:
    *   `script_source_file`: `data/scripts/items/potion_aggressive.lua` - The main Lua script that defines the aggressive potion's behavior.
    *   `script_death`: `data/scripts/items/potion_glass_break_temporary.lua` - A script executed when the potion breaks (e.g., on impact).

*   **`MaterialSuckerComponent`**:
    *   `barrel_size`: `500` - Defines the capacity or range of the material sucking effect.

## Lua Scripting

The behavior of the aggressive potion is primarily controlled by the Lua script located at `data/scripts/items/potion_aggressive.lua`. This script would handle effects such as:

*   What happens when the potion is thrown.
*   The area-of-effect or targeted damage/debuffs applied upon breaking.
*   Any unique interactions with the environment or enemies.

The `potion_glass_break_temporary.lua` script handles the visual and functional aspects of the potion breaking, likely creating a temporary effect or hazard.