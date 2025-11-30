---
title: Full HP Heart (Temple Variant)
category: entities
---

# Full HP Heart (Temple Variant)

This entity represents a full HP heart pickup specifically found in the Temple biome. It inherits its base functionality from `heart_fullhp.xml` but includes custom Lua scripting for its temple-specific behavior.

## Key Attributes

*   **`tags`**: `drillable`, `hittable`, `teleportable_NOT`
    *   Indicates the entity can be drilled, hit, and is explicitly *not* teleportable.

## Inheritance

*   **`Base file="data/entities/items/pickup/heart_fullhp.xml"`**: This entity inherits all properties and behaviors from the standard full HP heart.

## Lua Components

### `LuaComponent` (Item Picked Up)

*   **`script_item_picked_up="data/scripts/items/heart_fullhp_temple.lua"`**: This script is executed when the item is picked up by the player. It likely contains the logic for restoring the player's HP and any temple-specific effects.

### `LuaComponent` (Collision Trigger)

*   **`script_collision_trigger_hit="data/scripts/items/heart_fullhp_temple.lua"`**: This script is executed when the `CollisionTriggerComponent` is activated.
*   **`execute_every_n_frame="-1"`**: This ensures the script is executed only once when the trigger condition is met.

## Collision Trigger Component

*   **`width="24"`**, **`height="24"`**: Defines the bounding box dimensions for collision detection.
*   **`radius="32"`**: Specifies the collision radius.
*   **`required_tag="polymorphed_player"`**: The collision trigger will only activate if the colliding entity has the `polymorphed_player` tag. This suggests a specific interaction or condition for this heart in the Temple.
*   **`destroy_this_entity_when_triggered="0"`**: The heart will not be destroyed automatically when the collision trigger is activated. The Lua script will likely handle its destruction or state change.