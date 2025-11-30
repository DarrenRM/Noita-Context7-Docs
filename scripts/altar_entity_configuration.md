---
title: Altar Entity Configuration
category: data/entities
---

# Altar Entity Configuration

This document details the configuration of the Altar entity in Noita, focusing on its sacrifice mechanics and proximity-based effects.

## Altar Component

The `AltarComponent` defines the core functionality of the altar, specifically its sacrifice capabilities.

### Key Attributes:

*   **`recognized_entity_tags`**: A comma-separated list of entity tags that the altar will recognize as valid sacrifices. In this configuration, only entities tagged with `sacred_barrel` are accepted.
*   **`uses_remaining`**: The number of sacrifices the altar can perform before its functionality is depleted. Set to `100` in this example.

## Hitbox Component

The `HitboxComponent` defines the physical boundaries of the altar.

### Key Attributes:

*   **`aabb_min_x`**, **`aabb_max_x`**: Define the minimum and maximum X-coordinates of the altar's bounding box.
*   **`aabb_min_y`**, **`aabb_max_y`**: Define the minimum and maximum Y-coordinates of the altar's bounding box.

## Sacrifice Effects (on\_sacrifice Entity)

This nested `Entity` defines what happens when a valid sacrifice is made.

### Key Components:

*   **`MagicConvertMaterialComponent`**:
    *   **`from_material`**: The material that will be converted (e.g., `glowstone_altar`).
    *   **`to_material`**: The material it will be converted into (e.g., `blood`).
    *   **`radius`**: The area of effect for the material conversion.
    *   **`steps_per_frame`**: Controls the speed of the material conversion.
*   **`LuaComponent`**:
    *   **`script_source_file`**: Specifies a Lua script to execute upon sacrifice, likely for more complex effects like altar collapse.
    *   **`execute_on_added`**: If `1`, the script runs when the entity is added.
    *   **`execute_times`**: Controls how many times the script will execute.

## Proximity Effects (Torch Lighting)

This separate `Entity` block handles the visual effect of torches lighting up when the player approaches the altar.

### Key Components:

*   **`CollisionTriggerComponent`**:
    *   **`width`**, **`height`**: Define the dimensions of the trigger area.
    *   **`radius`**: The radius of the trigger area.
    *   **`required_tag`**: The tag of the entity that must enter the trigger area to activate it (e.g., `player_unit`).
*   **`LuaComponent`**:
    *   **`script_collision_trigger_hit`**: Specifies the Lua script to execute when the `CollisionTriggerComponent` is activated by a qualifying entity. This script (`data/scripts/buildings/altar_light_torches.lua`) handles the logic for lighting torches.
    *   **`execute_every_n_frame`**: Controls the frequency of script execution.

---