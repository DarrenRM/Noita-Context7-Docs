---
title: Touch Blood Projectile
category: entities
---

# Touch Blood Projectile

This entity defines a player projectile that converts materials and entities into blood upon contact.

## Key Components

### MagicConvertMaterialComponent (Primary)

This component handles the material conversion.

*   **`from_any_material`**: `1` (Converts any material)
*   **`to_material`**: `blood` (Converts to blood)
*   **`steps_per_frame`**: `3` (Number of conversion steps per frame)
*   **`loop`**: `0` (Conversion does not loop)
*   **`is_circle`**: `1` (Conversion area is a circle)
*   **`radius`**: `15` (Radius of the conversion circle in pixels)

### MagicConvertMaterialComponent (Secondary)

This component also handles material and entity conversion, with a larger radius and more steps.

*   **`from_any_material`**: `1` (Converts any material)
*   **`convert_entities`**: `1` (Also converts entities)
*   **`to_material`**: `blood` (Converts to blood)
*   **`steps_per_frame`**: `7` (Number of conversion steps per frame)
*   **`loop`**: `0` (Conversion does not loop)
*   **`is_circle`**: `1` (Conversion area is a circle)
*   **`radius`**: `30` (Radius of the conversion circle in pixels)

### LifetimeComponent

Determines how long the projectile exists.

*   **`lifetime`**: `4` (The projectile lasts for 4 seconds)

### AudioComponent

Defines the sound played when the projectile is active.

*   **`file`**: `data/audio/Desktop/projectiles.bank` (Path to the audio bank)
*   **`event_root`**: `player_projectiles/touch` (The root event for player projectile sounds)

## Inheritance

*   **`InheritTransformComponent`**: Indicates that this entity inherits transform properties, likely from its creator.