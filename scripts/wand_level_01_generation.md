---
title: Wand Level 01 Generation
category: scripts
---

---

# Wand Level 01 Generation

This script defines the parameters for generating a basic "Wand Level 01" in Noita. It utilizes the `gun_procedural.lua` library to create a procedural wand with specific characteristics.

## Core Generation Function

The primary function used is `generate_gun`.

### `generate_gun( mana, shuffle, always_random )`

*   **`mana`**: (Number) The base mana value for the wand.
    *   `30` in this case.
*   **`shuffle`**: (Boolean) Determines if the wand's spell order is shuffled.
    *   `1` (true) in this case, meaning the spell order will be randomized.
*   **`always_random`**: (Boolean) If true, all spells are always random.
    *   `false` in this case.

## Key Attributes (Implied by `generate_gun` parameters)

While the script is very concise, the `generate_gun` function implies the following key attributes for this wand:

*   **Base Mana**: 30
*   **Spell Shuffling**: Enabled
*   **Randomness**: Standard (not always random)

This setup suggests a relatively simple, early-game wand with a randomized spell order.