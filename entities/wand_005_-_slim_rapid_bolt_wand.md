---
title: Wand 005 - Slim Rapid Bolt Wand
category: entities
---

# Wand 005 - Slim Rapid Bolt Wand

This document details the configuration for "Wand 005", a wand entity in Noita, designed for AI-assisted modding.

## Core Entity Attributes

*   **name**: `wand_005` (Implicitly derived from filename)
*   **serialize**: `1` (Indicates the entity should be saved and loaded)
*   **tags**: `hittable` (Can be targeted by attacks)

## Transform Component

This component defines the initial position and rotation of the wand in the game world.

*   **position.x**: `689.705`
*   **position.y**: `-674.064`
*   **rotation**: `3.00811`
*   **scale.x**: `1`
*   **scale.y**: `-1` (Likely for sprite mirroring)

## Ability Component (Wand Functionality)

This is the primary component defining the wand's behavior.

*   **ui\_name**: "Slim Rapid bolt wand"
*   **sprite\_file**: `data/items_gfx/wands/wand_0484.png` (Visual representation)
*   **mana**: `210` (Maximum mana capacity)
*   **mana\_max**: `210`
*   **mana\_charge\_speed**: `52` (How quickly mana regenerates)
*   **charge\_wait\_frames**: `10` (Delay between shots)
*   **reload\_time\_frames**: `4` (Time to reload if applicable)
*   **item\_recoil\_max**: `1`
*   **item\_recoil\_offset\_coeff**: `1`
*   **item\_recoil\_recovery\_speed**: `15`
*   **item\_recoil\_rotation\_coeff**: `5`
*   **rotate\_in\_hand**: `1` (Wand rotates in hand)
*   **rotate\_in\_hand\_amount**: `1`
*   **use\_gun\_script**: `1` (Indicates it uses gun-like mechanics)
*   **amount\_in\_inventory**: `1`
*   **max\_amount\_in\_inventory**: `1`
*   **drop\_as\_item\_on\_death**: `1` (Drops as an item when the holder dies)

### Gun Config

*   **deck\_capacity**: `5` (Number of spells the wand can hold)
*   **reload\_time**: `4`
*   **shuffle\_deck\_when\_empty**: `1` (Shuffles spells when the deck is empty)
*   **actions\_per\_round**: `1`

### Gun Action Config (Default Action)

This defines the properties of the wand's primary projectile action.

*   **action\_type**: `0` (Standard projectile)
*   **speed\_multiplier**: `0.824541`
*   **spread\_degrees**: `6`
*   **fire\_rate\_wait**: `6` (Delay between firing actions)
*   **action\_mana\_drain**: `10` (Mana cost per shot)

## Audio Loop Component

*   **file**: `data/audio/Desktop/items.bank`
*   **event\_name**: `items/digger` (Likely a generic item sound)

## Hitbox Component

*   **aabb\_max\_x**: `4`
*   **aabb\_max\_y**: `4`
*   **aabb\_min\_x**: `-4`
*   **aabb\_min\_y**: `-4`
*   **_enabled**: `0` (Hitbox is disabled by default)

## Hotspot Component

Defines the firing position for projectiles.

*   **offset.x**: `8`
*   **offset.y**: `0`

## Item Component

General properties for the item.

*   **is\_pickable**: `1`
*   **is\_identified**: `1`
*   **play\_hover\_animation**: `1`

## Mana Reloader Component

*   **_enabled**: `1` (Wand can reload mana)

## Sprite Component

Defines the visual appearance of the wand.

*   **image\_file**: `data/items_gfx/wands/wand_0484.png`
*   **offset\_x**: `2`
*   **offset\_y**: `2`
*   **z\_index**: `0.595`

## Sprite Particle Emitter Component

Responsible for visual effects, likely a muzzle flash or projectile trail.

*   **sprite\_file**: `data/particles/ray.xml`
*   **color.r**: `1`
*   **color.g**: `1`
*   **color.b**: `1`
*   **color.a**: `0.5`
*   **scale\_velocity.x**: `-0.2`
*   **scale\_velocity.y**: `4`
*   **randomize\_velocity.max\_x**: `30`
*   **randomize\_velocity.max\_y**: `30`
*   **randomize\_velocity.min\_x**: `-30`
*   **randomize\_velocity.min\_y**: `-30`
*   **randomize\_position.max\_x**: `5`
*   **randomize\_position.max\_y**: `5`
*   **randomize\_position.min\_x**: `-5`
*   **randomize\_position.min\_y**: `-5`
*   **lifetime**: `1.5`

## Velocity Component

Defines physics properties when the wand is in the world.

*   **gravity\_y**: `400`
*   **terminal\_velocity**: `1000`
*   **mVelocity.y**: `650.486` (Initial upward velocity when dropped)

## Lua Component

This component links to a Lua script that likely handles procedural generation or specific wand behaviors.

*   **script\_source\_file**: `data/scripts/gun/procedural/level_1_wand.lua`
*   **execute\_on\_added**: `1`
*   **remove\_after\_executed**: `1`

## Base Component

Inherits properties from a base wand pickup entity.

*   **file**: `data/entities/base_wand_pickup.xml`