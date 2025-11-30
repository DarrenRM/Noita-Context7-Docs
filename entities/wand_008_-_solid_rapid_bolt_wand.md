---
title: Wand 008 - Solid Rapid Bolt Wand
category: entities
---

# Wand 008 - Solid Rapid Bolt Wand

This document details the configuration for "Wand 008", a wand entity in Noita, designed for AI-assisted modding.

## Core Entity Properties

*   **name**: `wand_008` (Implicitly defined by file name, not explicitly in XML)
*   **serialize**: `1` (Indicates the entity should be saved and loaded)
*   **tags**: `hittable` (The wand can be hit by projectiles or other entities)

## Ability Component (Wand Functionality)

This component defines the core behavior and stats of the wand.

*   **ui\_name**: `Solid Rapid bolt wand` (The name displayed in-game)
*   **sprite\_file**: `data/items_gfx/wands/wand_0898.png` (The visual representation of the wand)
*   **mana**: `160` (The maximum mana capacity of the wand)
*   **mana\_max**: `160` (Same as mana, defining the upper limit)
*   **mana\_charge\_speed**: `52` (How quickly mana regenerates)
*   **charge\_wait\_frames**: `10` (Delay between shots when holding the fire button)
*   **reload\_time\_frames**: `26` (Time it takes to reload the wand)
*   **item\_recoil\_max**: `1` (Maximum recoil applied when firing)
*   **item\_recoil\_rotation\_coeff**: `5` (Coefficient for rotational recoil)
*   **rotate\_in\_hand**: `1` (The wand rotates in the player's hand)
*   **rotate\_hand\_amount**: `0.7` (Amount of hand rotation)
*   **use\_gun\_script**: `1` (Indicates that a specific gun script is used for its behavior)

### Gun Configuration

Defines the wand's firing mechanics.

*   **deck\_capacity**: `7` (The number of spells the wand can hold in its "deck")
*   **reload\_time**: `26` (Reload time in frames, consistent with `AbilityComponent`)
*   **shuffle\_deck\_when\_empty**: `1` (The wand's spell deck will shuffle when it runs out of spells)
*   **actions\_per\_round**: `1` (Number of actions (spells) cast per shot)

### Gun Action Configuration (Default/Base)

This section defines the base properties for actions fired by the wand. Specific spell configurations will override these.

*   **action\_mana\_drain**: `10` (Mana cost per action)
*   **speed\_multiplier**: `0.987743` (Slightly reduces projectile speed)
*   **spread\_degrees**: `2` (Angular spread of projectiles)
*   **fire\_rate\_wait**: `10` (Wait time between firing actions within a single shot)

## Sprite Component

Handles the visual rendering of the wand.

*   **image\_file**: `data/items_gfx/wands/wand_0898.png` (The sprite used for the wand)
*   **offset\_x**: `2`
*   **offset\_y**: `2`
*   **z\_index**: `0.595` (Determines rendering order)
*   **update\_transform\_rotation**: `1` (The sprite's rotation updates with the entity's rotation)

## Sprite Particle Emitter Component

Responsible for visual effects, likely a subtle glow or aura.

*   **sprite\_file**: `data/particles/ray.xml` (The particle sprite used)
*   **color**: `r="1", g="1", b="1", a="0.5"` (White with 50% opacity)
*   **emission\_interval\_min\_frames**: `3`
*   **emission\_interval\_max\_frames**: `6` (Particles are emitted periodically)
*   **lifetime**: `1.5` (Particles last for 1.5 seconds)
*   **randomize\_position.max\_x**: `5`
*   **randomize\_position.max\_y**: `5`
*   **randomize\_velocity.max\_x**: `30`
*   **randomize\_velocity.max\_y**: `30` (Particles have randomized initial velocity and position)
*   **scale\_velocity.x**: `-0.2`
*   **scale\_velocity.y**: `4` (Particles shrink in X and grow in Y over their lifetime)
*   **velocity\_always\_away\_from\_center**: `1` (Particles move away from the emitter's center)

## Lua Component

Links the wand to a procedural script for generating its spell loadout.

*   **script\_source\_file**: `data/scripts/gun/procedural/level_1_wand.lua` (The script that defines the wand's initial spells)

## Base File

Inherits properties from a generic wand pickup entity.

*   **Base file**: `data/entities/base_wand_pickup.xml`

---