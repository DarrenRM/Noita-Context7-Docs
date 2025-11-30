---
title: Transmutation Explosion Entity
category: entities
---

# Transmutation Explosion Entity

This entity defines a magical explosion that transmutes materials within its radius.

## Key Components

### MagicConvertMaterialComponent

This component handles the material transmutation effect.

| Attribute       | Description                                                                 |
| :-------------- | :-------------------------------------------------------------------------- |
| `from_any_material` | If set to "1", it will transmute any material it encounters.                |
| `to_material`   | The target material to transmute into (e.g., "acid").                       |
| `steps_per_frame` | How many transmutation steps occur per game frame. Higher values mean faster transmutation. |
| `loop`          | If "0", the transmutation effect plays once. If "1", it loops.              |
| `is_circle`     | If "1", the transmutation occurs in a circular area.                        |
| `radius`        | The radius of the transmutation effect in pixels.                           |

### LifetimeComponent

This component determines how long the entity exists before despawning.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `lifetime`| The duration in seconds the entity will persist. |