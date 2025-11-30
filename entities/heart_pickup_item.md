---
title: Heart Pickup Item
category: entities
---

---

# Heart Pickup Item

This document describes the Noita entity configuration for the Heart pickup item. This item is typically found in the game world and grants the player an extra health point.

## Core Components

The Heart entity is defined by several key components that dictate its behavior and appearance.

### Entity Tags

The primary tags associated with this entity are:
- `drillable`: Indicates the entity can be destroyed by drills.
- `hittable`: The entity can be damaged by projectiles or other attacks.
- `teleportable_NOT`: The entity cannot be teleported.
- `item_pickup`: Marks this entity as an item that can be picked up.

### UIInfoComponent

This component provides information displayed in the game's user interface.
- `name`: `$item_heart` - This is a localization key that will resolve to "Heart" or a similar term in the game's language.

### ItemComponent

This component defines the item's properties related to pickup and inventory.
- `item_name`: `$item_heart` - Links to the same localization key as `UIInfoComponent`.
- `stats_count_as_item_pick_up`: `0` - This item does not count towards the player's total item pickup statistics.
- `play_pick_sound`: `0` - The default pickup sound is not played for this item.
- `auto_pickup`: `1` - The item is automatically picked up by the player when they are near it.

### LuaComponent

This component links to a Lua script that handles custom logic when the item is picked up.
- `script_item_picked_up`: `data/scripts/items/heart.lua` - This script contains the logic for what happens when the player collects the heart.

### LightComponent

This component adds a light source to the entity.
- `r`, `g`, `b`: `255`, `255`, `255` - The light is white.
- `radius`: `64` - The light illuminates an area with a radius of 64 pixels.
- `fade_out_time`: `0.75` - The light fades out over 0.75 seconds.

### SpriteComponent

This component defines the visual representation of the Heart item.
- `image_file`: `data/items_gfx/heart_extrahp.xml` - Specifies the graphical asset used for the heart.
- `offset_x`: `8` - The sprite is offset 8 pixels to the right.
- `offset_y`: `19` - The sprite is offset 19 pixels down.
- `z_index`: `20` - Determines the rendering order, ensuring it appears above other elements.

## Other Components

While not the primary focus, other components contribute to the item's basic functionality:

- **VelocityComponent**: Handles the item's movement and velocity.
- **SimplePhysicsComponent**: Manages basic physics interactions, such as gravity and collision.
- **HitboxComponent**: Defines the collision area of the item.
    - `aabb_min_x`, `aabb_max_x`, `aabb_min_y`, `aabb_max_y`: Defines the bounding box for collision detection.
    - `is_item`: `1` - Confirms this is an item.