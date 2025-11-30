---
title: Essence Laser Item Pickup
category: entities
---

# Essence Laser Item Pickup

This document details the configuration for the "Essence Laser" item pickup entity in Noita, intended for AI-assisted modding.

## Entity Definition

The core entity defines the Essence Laser as a pickup item.

```xml
<Entity tags="teleportable_NOT,essence,item_pickup">
    <!-- ... components ... -->
</Entity>
```

### Key Attributes:

*   **`tags`**:
    *   `teleportable_NOT`: Prevents this item from being teleported.
    *   `essence`: Identifies this as an essence type item.
    *   `item_pickup`: Marks this entity as an item that can be picked up.

## Components

### ItemComponent

Configures the basic properties of the item.

```xml
<ItemComponent
    item_name="$item_essence_laser"
    ui_description="$itemdesc_essence_laser"
    play_spinning_animation="0"
    stats_count_as_item_pick_up="0"
    >
</ItemComponent>
```

#### Key Attributes:

*   **`item_name`**: The internal name for the item, likely referencing a localization string for display.
*   **`ui_description`**: References a localization string for the item's tooltip description.
*   **`play_spinning_animation`**: Set to `0`, meaning the item does not play a spinning animation when on the ground.
*   **`stats_count_as_item_pick_up`**: Set to `0`, indicating this pickup does not contribute to general item pickup statistics.

### SpriteComponent

Defines the visual representation of the item.

```xml
<SpriteComponent
    image_file="data/items_gfx/essences/essence_laser.png"
    offset_x="8"
    offset_y="8"
    update_transform="1"
    update_transform_rotation="0"
    >
</SpriteComponent>
```

#### Key Attributes:

*   **`image_file`**: Path to the sprite image for the Essence Laser.
*   **`offset_x`**, **`offset_y`**: Adjusts the sprite's position relative to its entity origin.
*   **`update_transform`**: Set to `1`, indicating the sprite's transform (position, rotation, scale) should be updated.
*   **`update_transform_rotation`**: Set to `0`, meaning the sprite's rotation will not automatically follow the entity's rotation.

### VariableStorageComponent

Stores custom variables associated with the entity.

```xml
<VariableStorageComponent
    name="essence_id"
    value_string="laser"
    >
</VariableStorageComponent>
```

#### Key Attributes:

*   **`name`**: The name of the variable being stored (`essence_id`).
*   **`value_string`**: The string value assigned to the variable (`laser`), likely used to identify the type of essence.

### LuaComponent

Links the item pickup to a Lua script for custom behavior.

```xml
<LuaComponent
    script_item_picked_up="data/scripts/essences/essence_pickup.lua"
    >
</LuaComponent>
```

#### Key Attributes:

*   **`script_item_picked_up`**: Specifies the Lua script to execute when this item is picked up by the player. This script handles the logic for what happens when the Essence Laser is collected.