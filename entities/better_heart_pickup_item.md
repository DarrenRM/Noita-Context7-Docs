---
title: Better Heart Pickup Item
category: entities
---

---

# Better Heart Pickup Item

This document describes the configuration for a "Better Heart" pickup item in Noita, designed for AI-assisted modding. This item provides a health boost to the player.

## Entity Definition

The core of the item is defined by an `<Entity>` tag with several key components.

```xml
<Entity tags="drillable,hittable,teleportable_NOT,item_pickup">
    <!-- Components defining the item's behavior and appearance -->
</Entity>
```

### Key Tags:

*   `drillable`: The item can be destroyed by drills.
*   `hittable`: The item can be damaged by projectiles.
*   `teleportable_NOT`: The item cannot be teleported.
*   `item_pickup`: Identifies this entity as an item that can be picked up.

## Components

The following components define the item's physics, UI information, hitbox, item properties, scripting, lighting, and visual representation.

### VelocityComponent & SimplePhysicsComponent

These components define the basic physics of the item, allowing it to exist and interact within the game world. Specific parameters are not detailed here as they are standard for pickup items.

### UIInfoComponent

This component provides information displayed in the game's user interface.

```xml
<UIInfoComponent
    name="$item_heart_better"
    >
</UIInfoComponent>
```

*   `name`: `$item_heart_better` - This is a localization key for the item's name, which would be defined elsewhere in the game's localization files.

### HitboxComponent

Defines the physical boundaries of the item for collision detection.

```xml
<HitboxComponent
    _tags="enabled_in_world"
    aabb_min_x="-6"
    aabb_max_x="6"
    aabb_min_y="-8"
    aabb_max_y="0"
    is_enemy="0"
    is_item="1"
    is_player="0" >
</HitboxComponent>
```

*   `aabb_min_x`, `aabb_max_x`, `aabb_min_y`, `aabb_max_y`: Define the axis-aligned bounding box (AABB) for the hitbox.
*   `is_item="1"`: Crucially marks this as an item.

### ItemComponent

Configures the item's behavior when interacting with the player.

```xml
<ItemComponent
    item_name="$item_heart_better"
    play_spinning_animation="0"
    stats_count_as_item_pick_up="0"
    play_pick_sound="0"
    auto_pickup="1" >
</ItemComponent>
```

*   `item_name`: `$item_heart_better` - Links to the UI name.
*   `auto_pickup="1"`: The item will be automatically picked up by the player when they are near it.
*   `play_spinning_animation="0"`: Disables a spinning animation.
*   `stats_count_as_item_pick_up="0"`: This item does not count towards the player's total item pickup count for certain game mechanics.
*   `play_pick_sound="0"`: Disables the default pickup sound.

### LuaComponent

This component links the item to a Lua script that handles its specific functionality when picked up.

```xml
<LuaComponent
    script_item_picked_up="data/scripts/items/heart_better.lua" >
</LuaComponent>
```

*   `script_item_picked_up`: Points to the Lua script (`heart_better.lua`) that executes when the item is collected. This script would contain the logic for granting health.

### LightComponent

Adds a light source to the item, making it visually stand out.

```xml
<LightComponent
    _tags="enabled_in_world"
    _enabled="1"
    r="255"
    g="255"
    b="255"
    radius="64"
    fade_out_time="0.75" >
</LightComponent>
```

*   `r`, `g`, `b`: Set the light color to white (255, 255, 255).
*   `radius`: The range of the light effect.
*   `fade_out_time`: How long the light takes to fade.

### SpriteComponent

Defines the visual appearance of the item in the game world.

```xml
<SpriteComponent
    _tags="enabled_in_world,character"
    alpha="1"
    image_file="data/items_gfx/heart_extrahp.xml"
    offset_x="8"
    offset_y="19"
    z_index="20" >
</SpriteComponent>
```

*   `image_file`: `data/items_gfx/heart_extrahp.xml` - Specifies the graphical asset used for the item. This likely points to a definition of the heart sprite.
*   `offset_x`, `offset_y`: Adjust the sprite's position relative to the entity's origin.
*   `z_index`: Controls the rendering order of the sprite.