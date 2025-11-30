---
title: Workshop Exit Final Entity
category: entities
---

# Workshop Exit Final Entity

This document describes the `workshop_exit_final.xml` entity, which serves as the final exit point in the Noita workshop.

## Key Components

### `CollisionTriggerComponent`

This component defines the area that triggers an event when the player enters it.

| Attribute              | Description                                                                 |
| :--------------------- | :-------------------------------------------------------------------------- |
| `width`                | The width of the trigger area.                                              |
| `height`               | The height of the trigger area.                                             |
| `radius`               | The radius of the trigger area (used for circular detection).               |
| `destroy_this_entity_when_triggered` | If set to `1`, the entity will be destroyed when triggered. Set to `0` here. |
| `required_tag`         | The tag of the entity that must trigger this component (e.g., `player_unit`). |

### `LuaComponent`

This component links the entity to a Lua script for custom behavior.

| Attribute                 | Description                                                                                             |
| :------------------------ | :------------------------------------------------------------------------------------------------------ |
| `script_collision_trigger_hit` | The path to the Lua script that will be executed when the `CollisionTriggerComponent` is hit.           |
| `execute_every_n_frame`   | Determines how often the script is executed. `-1` means it executes only once when triggered.           |

## XML Structure

```xml
<Entity tags="workshop_exit" >
    <CollisionTriggerComponent
      width="52"
      height="52"
      radius="128"
      destroy_this_entity_when_triggered="0"
      required_tag="player_unit" >
  	</CollisionTriggerComponent>

    <LuaComponent
      script_collision_trigger_hit="data/scripts/buildings/workshop_exit_final.lua"
      execute_every_n_frame="-1" >
    </LuaComponent>
</Entity>
```