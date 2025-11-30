---
title: Touch Gold Projectile
category: entities
---

# Touch Gold Projectile

This entity defines a player projectile that converts materials and entities into gold upon contact.

## Key Components

### MagicConvertMaterialComponent (Primary)

This component handles the material conversion.

*   **`from_any_material`**: `1` (Can convert any material)
*   **`to_material`**: `"gold"` (Converts to gold)
*   **`steps_per_frame`**: `2` (Number of conversion steps per frame)
*   **`loop`**: `0` (Does not loop)
*   **`is_circle`**: `1` (Conversion area is a circle)
*   **`radius`**: `10` (Radius of the conversion circle in pixels)

### MagicConvertMaterialComponent (Secondary - Entity Conversion)

This component handles entity conversion.

*   **`from_any_material`**: `1` (Can convert any material)
*   **`convert_entities`**: `1` (Also converts entities)
*   **`to_material`**: `"gold"` (Converts to gold)
*   **`steps_per_frame`**: `7` (Higher steps for potentially more complex entity conversion)
*   **`loop`**: `0` (Does not loop)
*   **`is_circle`**: `1` (Conversion area is a circle)
*   **`radius`**: `30` (Larger radius for entity conversion)

### LifetimeComponent

Determines how long the projectile exists.

*   **`lifetime`**: `4` (The projectile lasts for 4 frames)

### AudioComponent

Handles the sound effect for the projectile.

*   **`file`**: `"data/audio/Desktop/projectiles.bank"` (The audio bank file)
*   **`event_root`**: `"player_projectiles/touch"` (The specific audio event to play)

## Inheritance

*   **`InheritTransformComponent`**: Indicates that this entity inherits transform properties, likely from its creator.

## Tags

*   **`projectile_player`**: Identifies this entity as a player-created projectile.