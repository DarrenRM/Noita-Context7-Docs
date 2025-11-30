---
title: Potion Item Configuration
category: scripts
---

# Potion Item Configuration

This document outlines the configuration for potion items in Noita, focusing on how their material composition and special properties are determined.

## Potion Material Definitions

Potions are composed of various liquid materials, each with an associated cost. These are categorized into standard and magic liquids.

### Standard Materials

| Material Name           | Cost |
| :---------------------- | :--- |
| `lava`                  | 300  |
| `water`                 | 200  |
| `blood`                 | 200  |
| `alcohol`               | 200  |
| `oil`                   | 200  |
| `slime`                 | 200  |
| `acid`                  | 400  |
| `radioactive_liquid`    | 300  |
| `gunpowder_unstable`    | 400  |
| `liquid_fire`           | 400  |
| `blood_cold`            | 300  |

### Magic Materials

| Material Name                     | Cost |
| :-------------------------------- | :--- |
| `magic_liquid_unstable_teleportation` | 500  |
| `magic_liquid_polymorph`          | 500  |
| `magic_liquid_random_polymorph`   | 500  |
| `magic_liquid_berserk`            | 500  |
| `magic_liquid_charm`              | 800  |
| `magic_liquid_invisibility`       | 800  |
| `material_confusion`              | 800  |
| `magic_liquid_movement_faster`    | 800  |
| `magic_liquid_faster_levitation`  | 800  |
| `magic_liquid_worm_attractor`     | 800  |
| `magic_liquid_protection_all`     | 800  |
| `magic_liquid_mana_regeneration`  | 500  |

## Potion Generation Logic (`init` function)

The `init` function determines the material of a potion when it is spawned. It uses a combination of random chance and specific game conditions.

### Key Generation Factors:

*   **Base Material Selection:**
    *   There's a 75% chance to select from `materials_magic` or `materials_standard`.
    *   The remaining 25% chance is for special or rare materials.

*   **Rare Material Chances:**
    *   `magic_liquid_hp_regeneration`: 0.05% chance.
    *   `purifying_powder`: A small chance within a specific random range.
    *   `magic_liquid_weakness`: A relatively rare chance.

*   **Seasonal/Event-Based Materials:**
    *   **May 1st/April 30th (Sima/Beer):** A 20% chance to spawn `sima` or `beer` during these dates.
    *   **Midsummer (Juhannus):** A 9% chance to spawn `juhannussima` or `beer` if Midsummer conditions are met.
    *   **Mammi Day:** A 10% chance to spawn `mammi` if Mammi Day conditions are met.
    *   **Valentine's Day (Feb 14th):** An 8% chance to spawn `magic_liquid_charm`.

*   **Extra Potion Capacity:**
    *   If the global variable `EXTRA_POTION_CAPACITY_LEVEL` is set above 1000, the potion's `barrel_size` is increased accordingly.
    *   The entity is tagged with `extra_potion_capacity`.

*   **Variable Storage Override:**
    *   The `potion_material` can be explicitly set via a `VariableStorageComponent` on the entity, overriding the random generation.

### `init` Function Summary:

The `init` function first sets a random seed based on the potion's position. It then proceeds through a series of conditional checks and random number generations to determine the `potion_material`. Special conditions related to game dates and global variables can influence the outcome, and a `VariableStorageComponent` can force a specific material. Finally, the determined material and its capacity are added to the entity.