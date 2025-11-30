---
title: Powder Stash Item Configuration
category: scripts
---

# Powder Stash Item Configuration

This document details the configuration for the `powder_stash.lua` script, which defines the behavior and contents of the Powder Stash item in Noita.

## Overview

The Powder Stash is an item that acts as a container for various powdered materials. Its primary function is to randomly generate a specific material and capacity upon initialization, allowing players to collect and store these materials.

## Key Attributes

### Material Generation

The Powder Stash randomly selects a material to store based on a weighted probability.

*   **Standard Materials:** These are common, non-magical materials.
    *   `sand` (cost: 300)
    *   `soil` (cost: 200)
    *   `snow` (cost: 200)
    *   `salt` (cost: 200)
    *   `coal` (cost: 200)
    *   `gunpowder` (cost: 200)
    *   `fungisoil` (cost: 200)
*   **Magic Materials:** These are rarer, magical materials.
    *   `copper` (cost: 500)
    *   `silver` (cost: 500)
    *   `gold` (cost: 500)
    *   `brass` (cost: 500)
    *   `bone` (cost: 800)
    *   `purifying_powder` (cost: 800)
    *   `fungi` (cost: 800)

The probability of generating a magic material is 75%, while standard materials have a 25% chance.

### Capacity

The capacity of the Powder Stash is determined by the global variable `EXTRA_POTION_CAPACITY_LEVEL`.

*   **Default Capacity:** If `EXTRA_POTION_CAPACITY_LEVEL` is not set or is less than or equal to 1000, the capacity defaults to 1000.
*   **Increased Capacity:** If `EXTRA_POTION_CAPACITY_LEVEL` is greater than 1000, this value is used as the `barrel_size` for the `MaterialSuckerComponent`. The entity also receives the `extra_potion_capacity` tag.

### Initialization (`init` function)

The `init` function is called when the Powder Stash entity is spawned.

1.  **Seed Generation:** A random seed is set based on the entity's position (`x`, `y`) to ensure consistent material generation for identical stashes.
2.  **Material Selection:** A material is randomly chosen from either the `materials_magic` or `materials_standard` tables based on the defined probabilities.
3.  **Capacity Determination:** The `total_capacity` is retrieved from the global variable `EXTRA_POTION_CAPACITY_LEVEL`.
4.  **Capacity Adjustment (if applicable):** If `total_capacity` exceeds 1000, the `MaterialSuckerComponent`'s `barrel_size` is updated, and the `extra_potion_capacity` tag is added.
5.  **Material Inventory:** The selected `potion_material` is added to the entity's inventory with the determined `total_capacity`.

## Modding Considerations

*   **Material Definitions:** The `materials_standard` and `materials_magic` tables can be modified to change the available materials, their costs, and their rarity.
*   **Capacity Control:** The `EXTRA_POTION_CAPACITY_LEVEL` global variable can be manipulated by other mods to alter the default capacity of Powder Stashes.
*   **Mod Overrides:** Be aware that other mods, such as `mods/nightmare potion.lua`, may overwrite this script's functionality.