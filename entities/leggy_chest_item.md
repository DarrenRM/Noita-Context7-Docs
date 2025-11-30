---
title: Leggy Chest Item
category: entities
---

# Leggy Chest Item

This document describes the `chest_leggy.xml` entity, which represents a special type of chest in Noita that has unique pickup behavior.

## Core Components

This entity utilizes several key components to define its behavior and appearance.

### UIInfoComponent
This component defines the in-game name of the item.

*   **name**: `$item_chest_treasure` - The internal identifier for the item's name, which will be displayed in the UI.

### PhysicsBodyComponent
This component governs the physical properties of the chest.

*   **allow\_sleep**: `1` - Allows the physics body to go to sleep when not in motion, optimizing performance.
*   **is\_bullet**: `1` - Treats the physics body as a bullet, enabling collision detection with other dynamic objects.
*   **auto\_clean**: `1` - Automatically removes the physics body when it's no longer needed.
*   **hax\_fix\_going\_through\_ground**: `1` - A workaround to prevent the physics body from clipping through the ground.

### PhysicsImageShapeComponent
This component defines the visual representation and collision shape of the chest.

*   **image\_file**: `data/buildings_gfx/chest_random.png` - The sprite used for the chest.
*   **material**: `wood_prop` - The material type, which can influence interactions with other game elements.

### ItemComponent
This component marks the entity as an item that can be picked up.

*   **item\_name**: `$item_chest_treasure` - Links to the UI name.
*   **stats\_count\_as\_item\_pick\_up**: `0` - This chest does not count towards the player's item pickup statistics.
*   **custom\_pickup\_string**: `$itempickup_open` - Displays a custom prompt when the player is near the chest, indicating it can be opened.
*   **play\_pick\_sound**: `0` - Disables the default pickup sound effect.

### LuaComponent
This component integrates custom Lua scripting to define advanced behaviors.

*   **script\_physics\_body\_modified**: `data/scripts/items/chest_leggy.lua` - Script executed when the physics body is modified.
*   **script\_item\_picked\_up**: `data/scripts/items/chest_leggy.lua` - Script executed when the item is picked up.
*   **script\_collision\_trigger\_hit**: `data/scripts/items/chest_leggy.lua` - Script executed when the collision trigger is hit.
*   **execute\_times**: `1` - The associated Lua scripts will execute only once.

### CollisionTriggerComponent
This component defines an area that triggers an event when a specific entity enters it.

*   **width**, **height**, **radius**: `30` - Defines the size of the trigger area.
*   **required\_tag**: `player_unit` - The trigger activates only when the player unit enters the area.

### LightComponent
This component adds a light source to the chest.

*   **r**, **g**, **b**: `255` - Sets the light color to white.
*   **radius**: `64` - The radius of the light emitted.
*   **fade\_out\_time**: `0.75` - The time it takes for the light to fade out.

## Key Functionality

The `chest_leggy.xml` entity's primary function is to act as a pickup item that, when interacted with by the player (indicated by the `$itempickup_open` string and the `CollisionTriggerComponent`), triggers custom Lua logic defined in `data/scripts/items/chest_leggy.lua`. This script likely handles the opening of the chest and the spawning of its contents. The `ItemComponent`'s `stats_count_as_item_pick_up: 0` suggests it's not meant to be collected as a standard inventory item but rather interacted with directly.