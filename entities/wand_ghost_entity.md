---
title: Wand Ghost Entity
category: entities
---

# Wand Ghost Entity

This document describes the `wand_ghost.xml` entity, which represents the Wand Ghost enemy in Noita.

## Key Attributes

The Wand Ghost is a mobile, ethereal enemy with specific behaviors and visual/audio components.

### Entity Tags

*   `mortal`: The entity can be killed.
*   `hittable`: The entity can be damaged by projectiles.
*   `homing_target`: The entity can be targeted by homing effects.
*   `wand_ghost`: A specific tag for this entity type.

### Base Entity

*   `file="data/entities/base_wand_ghost.xml"`: Inherits core properties from a base Wand Ghost definition.
    *   `CameraBoundComponent`:
        *   `_enabled="0"`: This component is disabled by default.
        *   `max_count="30"`: Limits the number of these entities that can be active.
        *   `distance="160000"`: Defines the radius within which the entity is considered by the camera.

### Lua Component

*   `_enabled="1"`: The Lua script is active.
*   `remove_after_executed="1"`: The entity will be removed after the script finishes execution.
*   `script_source_file="data/scripts/animals/wand_ghost.lua"`: Links to the primary script that defines the Wand Ghost's behavior.

### Audio Loop Component

*   `file="data/audio/Desktop/animals.bank"`: Specifies the audio bank containing the sound effects.
*   `event_name="animals/ghost/movement_loop"`: The name of the audio event for the ghost's movement loop.
*   `set_speed_parameter="1"`: Indicates that the audio's speed parameter should be controlled by the entity's movement speed.
*   `auto_play="1"`: The audio loop starts automatically when the entity is spawned.