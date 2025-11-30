---
title: Steel Chest Entity
category: entities
---

# Steel Chest Entity

This document describes the `chest_steel.xml` entity, which defines a steel chest in Noita. This chest functions as a container for items and has specific visual and physical properties.

## Key Components and Attributes

### Entity Tags
The primary tags for this entity are:
- `teleportable_NOT`: Prevents the chest from being teleported.
- `item_physics`: Indicates it's an item with physics properties.
- `chest`: Identifies it as a chest.

### UIInfoComponent
- `name`: `$item_chest_treasure` - This is a localization key for the chest's display name in the UI.

### PhysicsBodyComponent
This component defines the physical behavior of the chest.
- `uid`: `1` - Unique identifier for the physics body.
- `allow_sleep`: `1` - Allows the physics body to enter a sleep state when inactive.
- `auto_clean`: `1` - Automatically cleans up the physics body when no longer needed.
- `hax_fix_going_through_ground`: `1` - A workaround to prevent the chest from falling through the ground.

### PhysicsImageShapeComponent
This component defines the visual shape and material of the chest.
- `body_id`: `1` - Links this shape to the `PhysicsBodyComponent` with `uid="1"`.
- `image_file`: `data/buildings_gfx/chest_steel.png` - Specifies the sprite used for the chest.
- `material`: `steel` - Sets the material type, influencing interactions and appearance.

### ItemComponent
This component marks the entity as an item and controls its interaction as such.
- `item_name`: `$item_chest_treasure` - Matches the UI name.
- `stats_count_as_item_pick_up`: `0` - This chest does not count as a standard item pickup for statistics.
- `play_pick_sound`: `0` - No sound is played when the chest is picked up.

### LuaComponent (Scripting)
Two `LuaComponent` instances are used to attach scripts for specific behaviors.

#### Script 1: Physics Body Modification
- `script_physics_body_modified`: `data/scripts/buildings/chest_steel.lua` - This script is executed when the physics body is modified.
- `execute_times`: `1` - The script runs only once.

#### Script 2: Item Picked Up
- `script_item_picked_up`: `data/scripts/buildings/chest_steel.lua` - This script is executed when the item is picked up.

### LightComponent
This component adds a light source to the chest.
- `r`, `g`, `b`: `255`, `255`, `255` - Sets the light color to white.
- `radius`: `64` - Defines the range of the light.
- `fade_out_time`: `0.75` - Controls how long the light takes to fade out.