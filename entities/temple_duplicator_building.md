---
title: Temple Duplicator Building
category: entities
---

# Temple Duplicator Building

This document describes the `temple_duplicator.xml` entity, which represents a building in Noita.

## Overview

The Temple Duplicator is a building entity that, when triggered by a specific condition, executes a Lua script. It is primarily used for its functional behavior rather than its visual appearance.

## Key Components

### CollisionTriggerComponent

This component defines the collision area and the conditions under which the entity is triggered.

| Attribute              | Value | Description                                                                 |
| :--------------------- | :---- | :-------------------------------------------------------------------------- |
| `width`                | 32    | The width of the collision box.                                             |
| `height`               | 72    | The height of the collision box.                                            |
| `radius`               | 128   | The radius for trigger detection.                                           |
| `required_tag`         | `card_action` | The entity must have this tag to trigger the component.                     |
| `destroy_this_entity_when_triggered` | 0 | The entity will not be destroyed when triggered.                            |

### LuaComponent

This component links the entity to a Lua script that will be executed upon triggering.

| Attribute              | Value                                       | Description                                                                 |
| :--------------------- | :------------------------------------------ | :-------------------------------------------------------------------------- |
| `script_collision_trigger_hit` | `data/scripts/buildings/temple_duplicator.lua` | The path to the Lua script to execute when the `CollisionTriggerComponent` is hit. |
| `execute_every_n_frame` | -1                                          | The script will execute once when triggered, not repeatedly.                |

### SpriteComponent

This component defines the visual representation of the building.

| Attribute      | Value                               | Description                                                                 |
| :------------- | :---------------------------------- | :-------------------------------------------------------------------------- |
| `image_file`   | `data/buildings_gfx/temple_duplicator.xml` | The XML file defining the sprite's appearance.                              |
| `offset_x`     | 0                                   | Horizontal offset for the sprite.                                           |
| `offset_y`     | 0                                   | Vertical offset for the sprite.                                             |