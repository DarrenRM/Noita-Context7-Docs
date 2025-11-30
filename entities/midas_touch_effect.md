---
title: Midas Touch Effect
category: entities
---

# Midas Touch Effect

This entity defines a magical effect that transforms various materials into gold. It's likely used for visual flair or specific gameplay mechanics.

## Key Components

### MagicConvertMaterialComponent

This component is responsible for the material transformation. Multiple instances are used to define different source materials that can be converted.

| Attribute         | Description                                                                 |
| :---------------- | :-------------------------------------------------------------------------- |
| `kill_when_finished` | Whether the entity should be destroyed after the conversion is complete (0 = no). |
| `from_material`   | The material to be converted.                                               |
| `steps_per_frame` | How many conversion steps occur per frame. Higher values mean faster conversion. |
| `to_material`     | The material to convert into.                                               |
| `clean_stains`    | Whether to remove stains during conversion (0 = no).                        |
| `is_circle`       | Whether the conversion area is circular (1 = yes).                          |
| `radius`          | The radius of the conversion area.                                          |
| `_enabled`        | Whether this specific conversion rule is active (used to disable one rule). |

**Example Conversions:**

*   `ice_static` to `gold_static`
*   `ice_glass` to `gold_static`
*   `gold` to `gold_static`
*   `concrete_collapsed` to `gold_static`
*   `rock_hard_border` to `gold_static`
*   `templebrick_static` to `gold_static_dark` (this rule is disabled by default)

### LifetimeComponent

Determines how long the entity persists.

| Attribute            | Description                                       |
| :------------------- | :------------------------------------------------ |
| `lifetime`           | The base duration of the entity in frames.        |
| `randomize_lifetime` | Adds a random variation to the lifetime (min/max). |

### LoadEntitiesComponent

This component loads other entities, likely for visual effects.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `count.min` | Minimum number of entities to load.                                      |
| `count.max` | Maximum number of entities to load.                                      |
| `kill_entity` | Whether the parent entity should be destroyed after loading others (0 = no). |
| `entity_file` | The path to the entity file to load.                                     |

**Loaded Entity:**

*   `data/entities/particles/image_emitters/magical_symbol_fast.xml` - This suggests a visual particle effect associated with the Midas touch.