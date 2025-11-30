---
title: Wand Level 04 Generation
category: scripts
---

---

# Wand Level 04 Generation

This script defines the parameters for generating a specific tier of procedural wands in Noita. It utilizes the `gun_procedural.lua` library to create wands with a defined power level and complexity.

## Key Generation Parameters

The `generate_gun` function is called with the following arguments:

*   **Power Level:** `80` - This indicates a relatively high power level for the generated wands.
*   **Complexity:** `4` - This suggests a moderate to high number of spell slots and potential for complex spell combinations.
*   **Randomness:** `false` - This implies that the generation might be more deterministic or follow specific patterns for this level, rather than being purely random.

## Core Functionality

The script's primary purpose is to call the `generate_gun` function from `gun_procedural.lua`. This function is responsible for the actual procedural generation of wand properties, including:

*   **Spell Slots:** The number and arrangement of spell slots.
*   **Spell Capacity:** The maximum number of spells a wand can hold.
*   **Recharge Time:** How quickly the wand can be fired again.
*   **Mana Cost:** The mana required to cast spells from the wand.
*   **Projectile Speed:** The speed of projectiles fired by the wand.
*   **Spread:** The degree of spread for projectiles.
*   **Trigger Type:** Whether the wand fires automatically, on a timer, or with a delay.
*   **Spell Effects:** The types of spells that can be found on the wand.

The specific values for these properties are determined by the `generate_gun` function based on the provided power level and complexity.