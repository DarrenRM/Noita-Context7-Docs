---
title: Level 1 Wand (Good Rapid Bolt Wand)
category: entities
---

# Level 1 Wand (Good Rapid Bolt Wand)

This document details the configuration for a Level 1 Wand, specifically named "Good Rapid Bolt Wand" in-game. It's designed for AI-assisted modding by highlighting key attributes and their functions.

## Core Entity Properties

*   **name**: `base_wand_level_1` (Internal identifier)
*   **serialize**: `1` (Indicates the entity should be saved and loaded)
*   **tags**: `hittable` (Allows the wand to be targeted and damaged)

## Ability Component (Wand Functionality)

This component defines the core behavior of the wand.

*   **ui\_name**: `Good Rapid bolt wand` (The name displayed to the player)
*   **sprite\_file**: `data/items_gfx/wands/wand_0484.png` (Visual representation of the wand)
*   **mana**: `220` (Initial mana capacity)
*   **mana\_max**: `220` (Maximum mana capacity)
*   **mana\_charge\_speed**: `45` (Speed at which mana regenerates)
*   **charge\_wait\_frames**: `10` (Frames to wait before firing after a full charge)
*   **reload\_time\_frames**: `27` (Frames to reload the wand)
*   **item\_recoil\_max**: `1` (Maximum recoil applied when firing)
*   **item\_recoil\_rotation\_coeff**: `5` (Coefficient for rotation recoil)
*   **rotate\_in\_hand**: `1` (Enables hand rotation when holding the wand)
*   **rotate\_in\_hand\_amount**: `1` (Amount of hand rotation)

### Gun Configuration

Defines the firing mechanics of the wand.

*   **deck\_capacity**: `7` (Number of spell slots available)
*   **reload\_time**: `27` (Reload time in frames)
*   **shuffle\_deck\_when\_empty**: `1` (Wand shuffles its spell deck when empty)
*   **actions\_per\_round**: `1` (Number of actions performed per shot)

### Gun Action Configuration

Details the properties of a single spell cast.

*   **action\_mana\_drain**: `10` (Mana cost per action)
*   **speed\_multiplier**: `1.03398` (Multiplier for projectile speed)
*   **spread\_degrees**: `8` (Spread angle of projectiles)
*   **fire\_rate\_wait**: `2` (Wait time between firing actions in frames)

## Sprite Component (Visuals)

Handles the visual rendering of the wand.

*   **image\_file**: `data/items_gfx/wands/wand_0484.png` (The sprite image used)
*   **offset\_x**: `2`
*   **offset\_y**: `2`
*   **z\_index**: `0.595` (Rendering layer)

## Lua Component (Scripting)

This component executes a Lua script to define procedural wand generation.

*   **script\_source\_file**: `data/scripts/gun/procedural/level_1_wand.lua` (The script responsible for generating the wand's properties)
*   **execute\_on\_added**: `1` (Script runs when the entity is added)
*   **remove\_after\_executed**: `1` (Script is removed after execution)

## Other Notable Components

*   **AudioLoopComponent**: Handles sound effects associated with the wand.
*   **HitboxComponent**: Defines the collision area of the wand.
*   **HotspotComponent**: Specifies the firing position for projectiles.
*   **ItemComponent**: General item properties like pickability and identification.
*   **ManaReloaderComponent**: Allows the wand to passively regenerate mana.
*   **SpriteParticleEmitterComponent**: Creates visual particle effects, in this case, a "ray" effect.
*   **VelocityComponent**: Defines physics properties like gravity and terminal velocity when the wand is in the world.
*   **Base file="data/entities/base\_wand\_pickup.xml"**: Inherits properties from a base wand pickup entity.