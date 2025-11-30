---
title: Full HP Heart Pickup
category: entities
---

---

# Full HP Heart Pickup

This document describes the `heart_fullhp.xml` entity, which represents a pickup item in Noita that fully restores the player's health.

## Entity Definition

The core entity definition for the full HP heart pickup.

```xml
<Entity tags="drillable,hittable,teleportable_NOT,item_pickup">
  <!-- ... components ... -->
</Entity>
```

### Key Tags:

*   `drillable`: The entity can be destroyed by drills.
*   `hittable`: The entity can be damaged by projectiles.
*   `teleportable_NOT`: The entity cannot be teleported.
*   `item_pickup`: This entity is an item that can be picked up.

## Components

This section details the essential components that define the behavior and appearance of the full HP heart pickup.

### VelocityComponent

Handles the entity's velocity. In this case, it's empty, implying no initial velocity is set.

```xml
<VelocityComponent>
</VelocityComponent>
```

### SimplePhysicsComponent

Manages basic physics properties. Also empty, suggesting standard physics interactions.

```xml
<SimplePhysicsComponent>
</SimplePhysicsComponent>
```

### UIInfoComponent

Provides information displayed in the UI, such as the item's name.

```xml
<UIInfoComponent
  name="$item_heart_fullhp"
>
</UIInfoComponent>
```

*   `name`: Refers to a localization string for the item's name (e.g., "Heart").

### HitboxComponent

Defines the collision boundaries of the entity.

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

*   `aabb_min_x`, `aabb_max_x`, `aabb_min_y`, `aabb_max_y`: Define the axis-aligned bounding box for collision detection.
*   `is_item="1"`: Marks this entity as an item.

### ItemComponent

Specifies item-related properties.

```xml
<ItemComponent
  item_name="$item_heart_fullhp"
  play_spinning_animation="0"
  stats_count_as_item_pick_up="0"
  play_pick_sound="0"
  auto_pickup="1" >
</ItemComponent>
```

*   `item_name`: Links to the item's name in the UI.
*   `auto_pickup="1"`: The item is automatically picked up by the player when they are near it.

### LuaComponent

Attaches a Lua script to the entity for custom behavior.

```xml
<LuaComponent
  script_item_picked_up="data/scripts/items/heart_fullhp.lua" >
</LuaComponent>
```

*   `script_item_picked_up`: Specifies the Lua script to execute when the item is picked up. This script handles the health restoration logic.

### LightComponent

Adds a light source to the entity.

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

*   `r`, `g`, `b`: Define the color of the light (white in this case).
*   `radius`: The range of the light.
*   `fade_out_time`: How long the light takes to fade.

### SpriteComponent

Defines the visual representation of the entity.

```xml
<SpriteComponent
  _tags="enabled_in_world,character"
  alpha="1"
  image_file="data/items_gfx/heart.xml"
  offset_x="9"
  offset_y="18"
  z_index="20" >
</SpriteComponent>
```

*   `image_file`: Points to the sprite sheet or XML definition for the heart graphic.
*   `offset_x`, `offset_y`: Adjust the position of the sprite relative to the entity's origin.
*   `z_index`: Determines the drawing order of the sprite.