---
title: Status Effects List
category: scripts
---

# Status Effects List

This document details the status effects available in Noita, primarily for AI-assisted modding. It outlines key attributes for each status effect, focusing on their identification, UI representation, and associated game entities.

**Important Note for Modders:** To ensure compatibility and prevent serialization issues, **always add new status effects to the end of this list**. Never remove existing effects or change their order.

## Key Attributes of Status Effects

Each status effect is defined by a table with several key attributes:

*   **`id`**: A unique identifier for the status effect (e.g., "WET", "POISONED").
*   **`ui_name`**: A localization key for the display name of the status effect in the UI (e.g., `"$status_wet"`).
*   **`ui_description`**: A localization key for the detailed description of the status effect in the UI (e.g., `"$statusdesc_wet"`).
*   **`ui_icon`**: The file path to the icon displayed for the status effect in the UI.
*   **`effect_entity`**: The file path to an entity that handles the visual and/or functional aspects of the status effect. If empty (`""`), the effect might be purely visual or handled by other game logic. Custom game effect entities are also supported using `effect="CUSTOM"` and `custom_effect_id="UNIQUE_ID"`.
*   **`is_harmful`**: A boolean indicating whether the status effect is detrimental to the player.
*   **`protects_from_fire`**: A boolean indicating if the status effect provides immunity or resistance to fire.
*   **`remove_cells_that_cause_when_activated`**: A boolean that, when true, removes the cells that triggered this status effect upon activation.
*   **`min_threshold_normalized`**: For effects that have varying intensity or stages, this defines the normalized threshold at which this specific stage of the effect becomes active.
*   **`ui_timer_offset_normalized`**: Adjusts the displayed timer for the status effect in the UI, often used in conjunction with `min_threshold_normalized`.
*   **`effect_permanent`**: A boolean indicating if the status effect is permanent and cannot be removed by normal means.
*   **`extra_status_00`**: Allows for applying an additional status effect when this one is active, often used for combined effects.

## Status Effect Definitions

Below is a curated list of key status effects and their primary attributes.

### Defensive/Utility Effects

| ID                     | UI Name                 | UI Description          | UI Icon                                         | Protects from Fire | Effect Entity                                     |
| :--------------------- | :---------------------- | :---------------------- | :---------------------------------------------- | :----------------- | :------------------------------------------------ |
| `WET`                  | `$status_wet`           | `$statusdesc_wet`       | `data/ui_gfx/status_indicators/wet.png`         | `true`             | `data/entities/misc/effect_wet.xml`               |
| `OILED`                | `$status_oiled`         | `$statusdesc_oiled`     | `data/ui_gfx/status_indicators/oiled.png`       | `true`             | `data/entities/misc/effect_oiled.xml`             |
| `BLOODY`               | `$status_bloody`        | `$statusdesc_bloody`    | `data/ui_gfx/status_indicators/bloody.png`      | `true`             | `data/entities/misc/effect_bloody.xml`            |
| `SLIMY`                | `$status_slimy`         | `$statusdesc_slimy`     | `data/ui_gfx/status_indicators/slimy.png`       | `true`             | `data/entities/misc/effect_slimy.xml`             |
| `RADIOACTIVE`          | `$status_radioactive`   | `$statusdesc_radioactive` | `data/ui_gfx/status_indicators/radioactive.png` | `true`             | `data/entities/misc/effect_radioactive.xml`       |
| `HP_REGENERATION`      | `$status_hp_regeneration` | `$statusdesc_hp_regeneration` | `data/ui_gfx/status_indicators/hp_regeneration.png` | `false`            | `data/entities/misc/effect_regeneration.xml`      |
| `PROTECTION_ALL`       | `$status_protection_all` | `$statusdesc_protection_all` | `data/ui_gfx/status_indicators/protection_all.png` | `false`            | `data/entities/misc/effect_protection_all.xml`    |
| `MANA_REGENERATION`    | `$status_mana_regeneration` | `$statusdesc_mana_regeneration` | `data/ui_gfx/status_indicators/mana_regeneration.png` | `false`            | `data/entities/misc/effect_mana_regeneration.xml` |
| `INVISIBILITY`         | `$status_invisibility`  | `$statusdesc_invisibility` | `data/ui_gfx/status_indicators/invisibility.png` | `false`            | `data/entities/misc/effect_invisibility.xml`      |
| `NIGHTVISION`          | `$status_nightvision`   | `$statusdesc_nightvision` | `data/ui_gfx/status_indicators/nightvision.png` | `false`            | `data/entities/misc/effect_nightvision.xml`       |
| `PROTECTION_POLYMORPH` | `$status_protection_polymorph` | `$statusdesc_protection_polymorph` | `data/ui_gfx/status_indicators/protection_polymorph.png` | `false`            | `data/entities/misc/effect_protection_polymorph.xml` |

### Harmful Effects

| ID                     | UI Name                 | UI Description          | UI Icon                                         | Harmful | Effect Entity                               |
| :--------------------- | :---------------------- | :---------------------- | :---------------------------------------------- | :------ | :------------------------------------------ |
| `ALCOHOLIC`            | `$status_alcoholic`     | `$statusdesc_alcoholic` | `data/ui_gfx/status_indicators/alcoholic.png`   | `true`  | `data/entities/misc/effect_drunk.xml`       |
| `POISONED`             | `$status_poisoned`      | `$statusdesc_poisoned`  | `data/ui_gfx/status_indicators/poisoned.png`    | `true`  | `data/entities/misc/effect_poison.xml`      |
| `TELEPORTATION`        | `$status_teleportation` | `$statusdesc_teleportation` | `data/ui_gfx/status_indicators/teleportation.png` | `true`  | `data/entities/misc/effect_teleportation.xml` |
| `UNSTABLE_TELEPORTATION` | `$status_teleportation` | `$statusdesc_teleportation` | `data/ui_gfx/status_indicators/teleportation.png` | `true`  | `data/entities/misc/effect_unstable_teleportation.xml` |
| `POLYMORPH`            | `$status_polymorph`     | `$statusdesc_polymorph` | `data/ui_gfx/status_indicators/polymorph.png`   | `true`  | `data/entities/misc/effect_polymorph.xml`   |
| `POLYMORPH_RANDOM`     | `$status_polymorph_random` | `$statusdesc_polymorph_random` | `data/ui_gfx/status_indicators/polymorph_random.png` | `true`  | `data/entities/misc/effect_polymorph_random.xml` |
| `POLYMORPH_UNSTABLE`   | `$status_polymorph_random` | `$statusdesc_polymorph_random` | `data/ui_gfx/status_indicators/polymorph_random.png` | `true`  | `data/entities/misc/effect_polymorph_unstable.xml` |
| `POLYMORPH_CESSATION`  | `$status_polymorph_random` | `$statusdesc_polymorph_random` | `data/ui_gfx/status_indicators/polymorph_random.png` | `true`  | `data/entities/misc/effect_polymorph_cessation.xml` |
| `BERSERK`              | `$status_berserk`       | `$statusdesc_berserk`   | `data/ui_gfx/status_indicators/berserk.png`     | `true`  | `data/entities/misc/effect_berserk.xml`     |
| `ON_FIRE`              | `$status_on_fire`       | `$statusdesc_on_fire`   | `data/ui_gfx/status_indicators/on_fire.png`     | `true`  | `""`                                        |
| `CONFUSION`            | `$status_confusion`     | `$statusdesc_confusion` | `data/ui_gfx/status_indicators/confusion.png`   | `true`  | `data/entities/misc/effect_confusion.xml`   |
| `WORM_ATTRACTOR`       | `$status_worm_attractor` | `$statusdesc_worm_attractor` | `data/ui_gfx/status_indicators/worm_attractor.png` | `true`  | `data/entities/misc/effect_worm_attractor.xml` |
| `FOOD_POISONING`       | `$status_food_poisoning` | `$statusdesc_food_poisoning` | `data/ui_gfx/status_indicators/food_poisoning.png` | `true`  | `data/entities/misc/effect_food_poisoning.xml` |
| `INGESTION_MOVEMENT_SLOWER` | `$status_ingestion_movement_slower` | `$statusdesc_ingestion_movement_slower` | `data/ui_gfx/status_indicators/ingestion_movement_slower.png` | `true`  | `data/entities/misc/effect_movement_slower.xml` |
| `INGESTION_DAMAGE`     | `$status_ingestion_damage` | `$statusdesc_ingestion_damage` | `data/ui_gfx/status_indicators/ingestion_damage.png` | `true`  | `""` (UI only)                              |
| `INGESTION_EXPLODING`  | `$status_ingestion_exploding` | `$statusdesc_ingestion_exploding` | `data/ui_gfx/status_indicators/ingestion_exploding.png` | `true`  | `""` (UI only)                              |
| `INGESTION_FREEZING`   | `$status_ingestion_freezing` | `$statusdesc_ingestion_freezing` | `data/ui_gfx/status_indicators/ingestion_freezing.png` | `true`  | `data/entities/misc/effect_internal_ice.xml` |
| `FARTS`                | `$status_farts`         | `$statusdesc_farts`     | `data/ui_gfx/status_indicators/farts.png`       | `true`  | `data/entities/misc/effect_farts.xml`       |
| `INGESTION_ON_FIRE`    | `$status_internal_fire` | `$statusdesc_internal_fire` | `data/ui_gfx/status_indicators/internal_fire.png` | `true`  | `data/entities/misc/effect_internal_fire.xml` |
| `CURSE_CLOUD`          | `$status_curse_cloud_00` | `$statusdesc_curse_cloud_00` | `data/ui_gfx/status_indicators/curse_cloud.png` | `true`  | `data/entities/misc/effect_curse_cloud_00.xml` |
| `WEAKNESS`             | `$status_weakness`      | `$statusdesc_weakness`  | `data/ui_gfx/status_indicators/weakness.png`    | `true`  | `data/entities/misc/effect_weakness.xml`    |

### Multi-Stage/Variant Effects

Some status effects have multiple entries to represent different intensities or variations.

#### `INGESTION_DRUNK`

This status effect represents varying levels of intoxication.

| UI Name                       | UI Description                | UI Icon                                     | `min_threshold_normalized` | `effect_entity`                           | `extra_status_00` |
| :---------------------------- | :---------------------------- | :------------------------------------------ | :------------------------- | :---------------------------------------- | :---------------- |
| `$status_ingestion_alcoholic_00` | `$statusdesc_ingestion_alcoholic_00` | `data/ui_gfx/status_indicators/drunk.png`   | `0.0`                      | `data/entities/misc/effect_drunk.xml`     | `null`            |
| `$status_ingestion_alcoholic_01` | `$statusdesc_ingestion_alcoholic_01` | `data/ui_gfx/status_indicators/drunk.png`   | `0.25`                     | `data/entities/misc/effect_drunk.xml`     | `null`            |
| `$status_ingestion_alcoholic_02` | `$statusdesc_ingestion_alcoholic_02` | `data/ui_gfx/status_indicators/drunk.png`   | `0.75`                     | `data/entities/misc/effect_drunk_01.xml`  | `null`            |
| `$status_ingestion_alcoholic_02` | `$statusdesc_ingestion_alcoholic_02` | `data/ui_gfx/status_indicators/drunk.png`   | `1.0`                      | `data/entities/misc/effect_drunk_01.xml`  | `POISONED`        |

#### `TRIP`

Represents different stages of a "trip" effect.

| UI Name         | UI Description    | UI Icon                               | `min_threshold_normalized` | `effect_entity`                         |
| :-------------- | :---------------- | :------------------------------------ | :------------------------- | :-------------------------------------- |
| `$status_trip_00` | `$statusdesc_trip_00` | `data/ui_gfx/status_indicators/trip.png` | `0.0`                      | `data/entities/misc/effect_trip_00.xml` |
| `$status_trip_01` | `$statusdesc_trip_01` | `data/ui_gfx/status_indicators/trip.png` | `0.5`                      | `data/entities/misc/effect_trip_01.xml` |
| `$status_trip_02` | `$statusdesc_trip_02` | `data/ui_gfx/status_indicators/trip.png` | `1.5`                      | `data/entities/misc/effect_trip_02.xml` |
| `$status_trip_03` | `$statusdesc_trip_03` | `data/ui_gfx/status_indicators/trip.png` | `3.0`                      | `data/entities/misc/effect_trip_03.xml` |

#### `CURSE_CLOUD`

Different variations of curse clouds with distinct effects.

| UI Name                 | UI Description            | UI Icon                                   | `min_threshold_normalized` | `effect_entity`                           |
| :---------------------- | :------------------------ | :---------------------------------------- | :------------------------- | :---------------------------------------- |
| `$status_curse_cloud_00` | `$statusdesc_curse_cloud_00` | `data/ui_gfx/status_indicators/curse_cloud.png` | `0.0`                      | `data/entities/misc/effect_curse_cloud_00.xml` |
| `$status_curse_cloud_01` | `$statusdesc_curse_cloud_01` | `data/ui_gfx/status_indicators/curse_cloud.png` | `0.25`                     | `data/entities/misc/effect_curse_cloud_01.xml` |
| `$status_curse_cloud_02` | `$statusdesc_curse_cloud_02` | `data/ui_gfx/status_indicators/curse_cloud.png` | `0.75`                     | `data/entities/misc/effect_curse_cloud_02.xml` |

### Other Notable Effects

| ID                     | UI Name                 | UI Description          | UI Icon                                         | Effect Entity                               |
| :--------------------- | :---------------------- | :---------------------- | :---------------------------------------------- | :------------------------------------------ |
| `CHARM`                | `$status_charm`         | `$statusdesc_charm`     | `data/ui_gfx/status_indicators/charm.png`       | `data/entities/misc/effect_charm.xml`       |
| `MOVEMENT_FASTER_2X`   | `$status_movement_faster` | `$statusdesc_movement_faster` | `data/ui_gfx/status_indicators/movement_faster.png` | `data/entities/misc/effect_movement_faster_2x.xml` |
| `FASTER_LEVITATION`    | `$status_faster_levitation` | `$statusdesc_faster_levitation` | `data/ui_gfx/status_indicators/faster_levitation.png` | `data/entities/misc/effect_faster_levitation.xml` |
| `JARATE`               | `$status_jarate`        | `$statusdesc_jarate`    | `data/ui_gfx/status_indicators/jarate.png`      | `data/entities/misc/effect_jarate.xml`      |
| `HYDRATED`             | `$status_oiled`         | `$statusdesc_oiled`     | `data/ui_gfx/status_indicators/oiled.png`       | `data/entities/misc/effect_oiled.xml`       |
| `RAINBOW_FARTS`        | `$status_rainbow_farts` | `$statusdesc_rainbow_farts` | `data/ui_gfx/status_indicators/farts.png`       | `data/entities/misc/effect_rainbow_farts.xml` |
| `MAMMI_EATER`          | `$status_mammi_eater`   | `$statusdesc_mammi_eater` | `data/ui_gfx/status_indicators/mammi_eater.png` | `null` (Permanent effect)                   |

**Note:** The `MAMMI_EATER` status effect is marked as `effect_permanent=true` and does not have an associated `effect_entity` in this definition, implying its effect is managed differently or is a purely persistent state.

This documentation provides a foundational understanding of Noita's status effects for modding purposes. For detailed implementation of `effect_entity` components, refer to the respective entity XML files.