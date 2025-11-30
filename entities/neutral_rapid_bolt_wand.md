---
title: Neutral Rapid Bolt Wand
category: entities
---

# Neutral Rapid Bolt Wand

This document details the configuration of the "Neutral Rapid Bolt Wand" entity in Noita, designed for AI-assisted modding.

## Core Entity Attributes

*   **name**: `wand_003` (Internal identifier)
*   **serialize**: `1` (Indicates the entity should be saved and loaded)
*   **tags**: `hittable` (The wand can be hit by projectiles or other entities)

## AbilityComponent - Wand Functionality

This component defines the core behavior and stats of the wand.

*   **ui\_name**: "Neutral Rapid bolt wand" (The name displayed in-game)
*   **mana**: `180` (Maximum mana capacity)
*   **mana\_max**: `180` (Maximum mana capacity)
*   **mana\_charge\_speed**: `54` (Speed at which mana regenerates)
*   **charge\_wait\_frames**: `10` (Frames to wait before firing after a full charge)
*   **reload\_time\_frames**: `90` (Frames to reload the wand)
*   **item\_recoil\_max**: `1` (Maximum recoil applied when firing)
*   **item\_recoil\_offset\_coeff**: `1` (Coefficient for recoil offset)
*   **item\_recoil\_recovery\_speed**: `15` (Speed at which recoil recovers)
*   **item\_recoil\_rotation\_coeff**: `5` (Coefficient for recoil rotation)
*   **rotate\_in\_hand**: `1` (Wand rotates in the player's hand)
*   **rotate\_in\_hand\_amount**: `0.7` (Amount of rotation in hand)
*   **sprite\_file**: `data/items_gfx/wands/wand_0958.png` (Visual sprite for the wand)
*   **use\_gun\_script**: `1` (Indicates the wand uses gun-specific scripting)

### gun\_config

Defines the deck and reloading behavior.

*   **deck\_capacity**: `6` (Number of spells the wand can hold in its deck)
*   **reload\_time**: `90` (Frames to reload)
*   **shuffle\_deck\_when\_empty**: `1` (The wand shuffles its deck when it runs out of spells)
*   **actions\_per\_round**: `1` (Number of actions (spells) cast per shot)

### gunaction\_config

Defines the properties of the spells cast by the wand.

*   **speed\_multiplier**: `0.994967` (Slightly reduces projectile speed)
*   **spread\_degrees**: `-3` (Applies a slight spread to projectiles)
*   **action\_mana\_drain**: `10` (Mana cost per spell cast)
*   **fire\_rate\_wait**: `2` (Frames to wait between firing actions within a single shot)

## SpriteComponent - Visuals

Defines the visual representation of the wand.

*   **image\_file**: `data/items_gfx/wands/wand_0958.png` (The sprite file used for the wand)
*   **offset\_x**: `2` (X-axis offset for the sprite)
*   **offset\_y**: `3` (Y-axis offset for the sprite)
*   **z\_index**: `0.595` (Determines the rendering order of the sprite)

## SpriteParticleEmitterComponent - Visual Effects

Responsible for particle effects associated with the wand.

*   **sprite\_file**: `data/particles/ray.xml` (The particle effect sprite)
*   **lifetime**: `1.5` (Duration of each particle in seconds)
*   **emission\_interval\_min\_frames**: `3` (Minimum frames between particle emissions)
*   **emission\_interval\_max\_frames**: `6` (Maximum frames between particle emissions)
*   **randomize\_position.max\_x**: `5` (Maximum random X offset for particle position)
*   **randomize\_position.max\_y**: `5` (Maximum random Y offset for particle position)
*   **randomize\_velocity.max\_x**: `30` (Maximum random X velocity for particles)
*   **randomize\_velocity.max\_y**: `30` (Maximum random Y velocity for particles)
*   **scale\_velocity.x**: `-0.2` (Rate at which particle scale decreases on the X-axis)
*   **scale\_velocity.y**: `4` (Rate at which particle scale increases on the Y-axis)
*   **color.r**: `1`, **color.g**: `1`, **color.b**: `1`, **color.a**: `0.5` (Initial color of the particles)
*   **color\_change.a**: `-0.5` (Rate at which particle alpha decreases)

## LuaComponent - Scripting

*   **script\_source\_file**: `data/scripts/gun/procedural/level_1_wand.lua` (The Lua script that governs procedural generation of spells for this wand)
*   **execute\_on\_added**: `1` (The script runs when the wand is added to the game)
*   **remove\_after\_executed**: `1` (The script is removed after it has executed once)

## Base File

*   **Base file**: `data/entities/base_wand_pickup.xml` (Inherits properties from the base wand pickup entity)