---
title: Evil Heart Pickup Item
category: entities
---

---

# Evil Heart Pickup Item

This document describes the `heart_evil.xml` entity, which represents an "Evil Heart" pickup item in Noita. This item is designed to be picked up by the player and likely affects their health or provides some other benefit/detriment.

## Key Components and Attributes

The `heart_evil.xml` entity is composed of several components, each contributing to its behavior and appearance.

### Entity Tags

The primary tags associated with this entity are:
- `drillable`: Indicates the entity can be destroyed by drills.
- `hittable`: The entity can be damaged by attacks.
- `teleportable_NOT`: The entity cannot be teleported.
- `item_pickup`: Marks this entity as an item that can be picked up.

### VelocityComponent

This component is present but empty, suggesting that the entity's initial velocity is handled by other means or defaults to zero.

### SimplePhysicsComponent

This component is also present but empty, indicating that the entity utilizes default physics properties.

### UIInfoComponent

- `name`: `$item_heart` - This is a localization key for the item's display name in the UI.

### HitboxComponent

Defines the physical boundaries of the item for interactions.
- `aabb_min_x`, `aabb_max_x`, `aabb_min_y`, `aabb_max_y`: Define the axis-aligned bounding box for the hitbox.
- `is_enemy`: `0` - Not an enemy.
- `is_item`: `1` - It is an item.
- `is_player`: `0` - Not the player.

### ItemComponent

Configures the item's behavior when interacted with.
- `item_name`: `$item_heart` - Links to the UI name.
- `play_spinning_animation`: `0` - The item does not play a spinning animation.
- `stats_count_as_item_pick_up`: `0` - This pickup does not count towards general item pickup statistics.
- `play_pick_sound`: `0` - No specific sound is played upon pickup.
- `auto_pickup`: `1` - The item is automatically picked up by the player when they are near it.

### LuaComponent

This component links the item's pickup behavior to a script.
- `script_item_picked_up`: `data/scripts/items/heart_evil.lua` - This script is executed when the item is picked up.

### LightComponent

Adds a light source to the item.
- `r`, `g`, `b`: `255`, `255`, `255` - The light is white.
- `radius`: `64` - The light has a radius of 64 units.
- `fade_out_time`: `0.75` - The light fades out over 0.75 seconds.

### SpriteComponent

Defines the visual representation of the item.
- `alpha`: `1` - Fully opaque.
- `image_file`: `data/items_gfx/heart_extrahp_evil.xml` - Specifies the graphical asset for the item.
- `offset_x`, `offset_y`: `8`, `19` - Adjusts the sprite's position relative to its origin.
- `z_index`: `20` - Determines the rendering order, placing it above most other world elements.