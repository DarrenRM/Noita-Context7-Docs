---
title: Wand Level 05 Procedural Generation
category: scripts
---

# Wand Level 05 Procedural Generation

This script defines the parameters for generating a Level 05 wand in Noita. It utilizes the `generate_gun` function from `gun_procedural.lua` to create a wand with specific characteristics.

## Key Generation Parameters

The `generate_gun` function is called with the following arguments:

*   **`100`**: This likely represents a base "power" or "rarity" value for the wand. Higher values generally lead to more potent or complex wands.
*   **`5`**: This parameter probably influences the number of spells or spell slots available on the wand. A value of 5 suggests a moderately sized wand.
*   **`false`**: This boolean likely controls whether the wand is guaranteed to have a specific, pre-defined spell or if it's entirely procedurally generated. `false` indicates a fully procedural generation.

## Core Functionality

The script's primary purpose is to invoke the `generate_gun` function, which handles the complex logic of procedurally assembling a wand based on various internal game mechanics and probabilities. This includes:

*   **Spell Selection**: Determining which spells are added to the wand.
*   **Spell Ordering**: Arranging spells in a functional sequence.
*   **Modifier Application**: Adding modifiers that affect spell behavior (e.g., speed, damage, spread).
*   **Stat Assignment**: Setting wand properties like recharge time, mana, and cast delay.

## Usage

This script is intended to be called by the game's procedural generation system when a Level 05 wand is required. It does not require direct user interaction.

```lua
dofile_once("data/scripts/gun/procedural/gun_procedural.lua")

generate_gun( 100, 5, false )
```