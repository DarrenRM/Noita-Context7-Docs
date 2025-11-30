---
title: Essence Alcohol Item Pickup
category: entities
---

---

# Essence Alcohol Item Pickup

This document describes the `essence_alcohol.xml` entity, which represents the "Alcohol" essence pickup item in Noita. This item is designed to be collected by the player and likely contributes to a resource or progression system.

## Key Components and Attributes

### Entity Tags
The entity has the following tags:
- `teleportable_NOT`: Indicates this entity cannot be teleported.
- `essence`: Marks it as an essence type item.
- `item_pickup`: Identifies it as an item that can be picked up.

### ItemComponent
This component defines the item's properties for the game's UI and inventory system.
- `item_name`: `$item_essence_alcohol` - The internal name for the item, likely linked to a localization string for display.
- `ui_description`: `$itemdesc_essence_alcohol` - The internal name for the item's description, also linked to localization.
- `play_spinning_animation`: `0` - The item does not play a spinning animation when on the ground.
- `stats_count_as_item_pick_up`: `0` - Picking up this item does not count towards general item pickup statistics.

### SpriteComponent
This component handles the visual representation of the item.
- `image_file`: `data/items_gfx/essences/essence_alcohol.png` - The path to the sprite image for the Alcohol essence.
- `offset_x`: `8` - Horizontal offset for the sprite.
- `offset_y`: `8` - Vertical offset for the sprite.
- `update_transform`: `1` - The sprite's transform (position, rotation) is updated.
- `update_transform_rotation`: `0` - The sprite's rotation is not updated independently.

### VariableStorageComponent
This component stores custom variables associated with the entity.
- `name`: `essence_id` - The name of the variable.
- `value_string`: `alcohol` - The string value assigned to `essence_id`, identifying this specific essence.

### LuaComponent
This component links the entity to Lua scripts for custom behavior.
- `script_item_picked_up`: `data/scripts/essences/essence_pickup.lua` - This script is executed when the item is picked up by the player. It likely handles the logic for what happens when the Alcohol essence is collected.