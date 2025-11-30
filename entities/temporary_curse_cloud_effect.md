---
title: Temporary Curse Cloud Effect
category: entities
---

# Temporary Curse Cloud Effect

This entity defines a temporary curse cloud effect in Noita. It inherits its base functionality from `effect_curse_cloud_01.xml` and adds a specific temporary duration.

## Key Attributes

*   **`tags`**: `curse_cloud` - Identifies this entity as a curse cloud.
*   **`Base file`**: `data/entities/misc/effect_curse_cloud_01.xml` - Inherits core properties from the base curse cloud entity.

## GameEffectComponent

This component defines the specific game effect applied by the cloud.

*   **`effect`**: `CUSTOM` - Indicates a custom effect is being used.
*   **`custom_effect_id`**: `CURSE_CLOUD_01_TEMPORARY` - A unique identifier for this specific temporary curse cloud effect.
*   **`frames`**: `600` - The duration of the effect in game frames (600 frames is equivalent to 10 seconds at 60 FPS).