---
title: Fungal Shift Magic
category: scripts
---

# Fungal Shift Magic

This script defines the "Fungal Shift" magic, a powerful spell that mutates materials throughout the world. It has a cooldown and a limited number of uses per run.

## Core Functionality

The `fungal_shift` function is the heart of this magic. It randomly selects a material to convert *from* and a material to convert *to*, then applies this transformation globally.

### Key Attributes

*   **`materials_from`**: A table defining the possible materials that can be converted. Each entry includes a `probability` and a list of `materials` that can be transformed. Some entries also have a `name_material` for clearer logging.
*   **`materials_to`**: A table defining the possible materials that can be converted *into*. Each entry has a `probability` and the target `material`.
*   **`log_messages`**: A list of strings used for in-game messages to describe the reality mutation.
*   **`greedy_materials`**: A list of materials that are less likely to be converted into if they are selected as the target material, to prevent undesirable outcomes.

## Material Conversion Logic

The script prioritizes converting materials based on weighted probabilities.

### `materials_from` Table

| Probability | Materials                                                              | Name Material (Optional) |
| :---------- | :--------------------------------------------------------------------- | :----------------------- |
| 1.0         | `water`, `water_static`, `water_salt`, `water_ice`                     | `water`                  |
| 1.0         | `lava`                                                                 |                          |
| 1.0         | `radioactive_liquid`, `poison`, `material_darkness`                    | `radioactive_liquid`     |
| 1.0         | `oil`, `swamp`, `peat`                                                 | `oil`                    |
| 1.0         | `blood`                                                                |                          |
| 1.0         | `blood_fungi`, `fungi`, `fungisoil`                                    | `fungi`                  |
| 1.0         | `blood_cold`, `blood_worm`                                             |                          |
| 1.0         | `acid`                                                                 |                          |
| 0.4         | `acid_gas`, `acid_gas_static`, `poison_gas`, `fungal_gas`, `radioactive_gas`, `radioactive_gas_static` | `acid_gas`               |
| 0.4         | `magic_liquid_polymorph`, `magic_liquid_unstable_polymorph`            | `magic_liquid_polymorph` |
| 0.4         | `magic_liquid_berserk`, `magic_liquid_charm`, `magic_liquid_invisibility` |                          |
| 0.6         | `diamond`                                                              |                          |
| 0.6         | `silver`, `brass`, `copper`                                            |                          |
| 0.2         | `steam`, `smoke`                                                       |                          |
| 0.4         | `sand`                                                                 |                          |
| 0.4         | `snow_sticky`                                                          |                          |
| 0.05        | `rock_static`                                                          |                          |
| 0.0003      | `gold`, `gold_box2d`                                                   | `gold`                   |

### `materials_to` Table

| Probability | Material                               |
| :---------- | :------------------------------------- |
| 1.00        | `water`                                |
| 1.00        | `lava`                                 |
| 1.00        | `radioactive_liquid`                   |
| 1.00        | `oil`                                  |
| 1.00        | `blood`                                |
| 1.00        | `blood_fungi`                          |
| 1.00        | `acid`                                 |
| 1.00        | `water_swamp`                          |
| 1.00        | `alcohol`                              |
| 1.00        | `sima`                                 |
| 1.00        | `blood_worm`                           |
| 1.00        | `poison`                               |
| 1.00        | `vomit`                                |
| 1.00        | `pea_soup`                             |
| 1.00        | `fungi`                                |
| 0.80        | `sand`                                 |
| 0.80        | `diamond`                              |
| 0.80        | `silver`                               |
| 0.80        | `steam`                                |
| 0.50        | `rock_static`                          |
| 0.50        | `gunpowder`                            |
| 0.50        | `material_darkness`                    |
| 0.50        | `material_confusion`                   |
| 0.20        | `rock_static_radioactive`              |
| 0.02        | `magic_liquid_polymorph`               |
| 0.02        | `magic_liquid_random_polymorph`        |
| 0.15        | `magic_liquid_teleportation`           |
| 0.10        | `mimic_liquid`                         |
| 0.01        | `urine`                                |
| 0.01        | `poo`                                  |
| 0.01        | `void_liquid`                          |
| 0.01        | `cheese_static`                        |

## Player Interaction & Effects

The spell can be influenced by the player's currently held item.

### Held Item Influence

*   If the player is holding a potion or powder stash, its main material has a chance (75%) to be used as either the `from` or `to` material.
*   Special handling exists for `gold` and `grass_holy` to prevent undesirable conversions.

### Cooldown and Limits

*   **Global Cooldown**: The spell has a long cooldown of 5 hours (60\*60\*5 seconds) between uses.
*   **Iteration Limit**: The spell can only be used a maximum of 20 times per run.

### Visual and Audio Feedback

*   When the spell is successfully cast, particles of the new material are spawned.
*   Music fades out and a specific "tripping balls" track is triggered.
*   A "treble eye" particle effect is created.
*   Important in-game messages are displayed, along with a UI icon indicating the "reality mutation" status.

## AI Modding Considerations

*   **Material Identification**: Modders can extend `materials_from` and `materials_to` with new or custom materials. Ensure these materials are correctly registered in the game's cell factory.
*   **Probability Tuning**: Adjusting the `probability` values in both tables will significantly alter the frequency and outcome of fungal shifts.
*   **Greedy Material Logic**: The `greedy_materials` list can be expanded to prevent specific materials from being converted into too often.
*   **Held Item Integration**: The `get_held_item_material` function can be modified to include other item types that might influence the fungal shift.
*   **Custom Log Messages**: The `log_messages` table can be populated with custom strings for unique mutation descriptions.
*   **Debug Mode**: The `debug_no_limits` parameter in the `fungal_shift` function can be used to bypass cooldowns and iteration limits for testing.
*   **Ban List**: The `[NO_FUNGAL_SHIFT]` tag can be applied to materials to prevent them from being targeted by the fungal shift.