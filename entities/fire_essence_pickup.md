---
title: Fire Essence Pickup
category: entities
---

# Fire Essence Pickup

This document describes the configuration for the Fire Essence pickup item in Noita, intended for AI-assisted modding.

## Entity Definition

The core entity defines the Fire Essence as a pickup item with specific properties.

```xml
<Entity tags="teleportable_NOT,essence,item_pickup">
	<!-- ... components ... -->
</Entity>
```

### Key Tags:
*   `teleportable_NOT`: Prevents this item from being teleported.
*   `essence`: Identifies this entity as an essence type.
*   `item_pickup`: Marks this entity as an item that can be picked up.

## Item Component

Configures the item's in-game properties and how it's presented to the player.

```xml
<ItemComponent
	item_name="$item_essence_fire"
	ui_description="$itemdesc_essence_fire"
	play_spinning_animation="0"
	stats_count_as_item_pick_up="0"
	>
</ItemComponent>
```

### Key Attributes:
*   `item_name`: The internal name for the item, often linked to localization strings (e.g., `$item_essence_fire`).
*   `ui_description`: The internal name for the item's tooltip description, also linked to localization strings (e.g., `$itemdesc_essence_fire`).
*   `play_spinning_animation`: Set to `0` to disable a spinning animation when the item is on the ground.
*   `stats_count_as_item_pick_up`: Set to `0` to prevent this pickup from contributing to general item pickup statistics.

## Sprite Component

Defines the visual representation of the Fire Essence.

```xml
<SpriteComponent
	image_file="data/items_gfx/essences/essence_fire.png"
	offset_x="8"
	offset_y="8"
	update_transform="1"
	update_transform_rotation="0"
	>
</SpriteComponent>
```

### Key Attributes:
*   `image_file`: Path to the sprite image for the Fire Essence.
*   `offset_x`, `offset_y`: Adjusts the sprite's position relative to the entity's center.
*   `update_transform`: Set to `1` to allow the sprite's position and rotation to be updated by the entity's transform.
*   `update_transform_rotation`: Set to `0` to prevent the sprite from inheriting rotation from the entity's transform.

## Variable Storage Component

Stores custom variables associated with the entity.

```xml
<VariableStorageComponent
	name="essence_id"
	value_string="fire"
	>
</VariableStorageComponent>
```

### Key Attributes:
*   `name`: The name of the variable (e.g., `essence_id`).
*   `value_string`: The string value assigned to the variable (e.g., `fire`), used to identify the type of essence.

## Lua Component

Links the item pickup to a script that handles its behavior when picked up.

```xml
<LuaComponent
	script_item_picked_up="data/scripts/essences/essence_pickup.lua"
	>
</LuaComponent>
```

### Key Attributes:
*   `script_item_picked_up`: Specifies the Lua script file to execute when the item is picked up by the player. This script likely handles the logic for granting the essence effect.