---
title: Touch Water Projectile
category: entities
---

# Touch Water Projectile

This entity defines a projectile that converts materials and entities it touches into water.

## Key Components

### MagicConvertMaterialComponent (x2)

This component is responsible for the material conversion effect. The entity has two instances of this component, likely for different conversion radii or step counts.

*   **`from_any_material`**: `1` (Converts any material)
*   **`to_material`**: `water` (Converts to water)
*   **`steps_per_frame`**: Controls the intensity/speed of the conversion.
    *   First instance: `4`
    *   Second instance: `7`
*   **`loop`**: `0` (Conversion happens once)
*   **`is_circle`**: `1` (Conversion area is circular)
*   **`radius`**: The size of the conversion area.
    *   First instance: `20`
    *   Second instance: `30`
*   **`convert_entities`**: `1` (Also converts entities within the radius to water) - *Only present on the second instance.*

### LifetimeComponent

Determines how long the projectile exists before disappearing.

*   **`lifetime`**: `4` (seconds)

### AudioComponent

Handles the sound effect played when the projectile is active.

*   **`file`**: `data/audio/Desktop/projectiles.bank`
*   **`event_root`**: `player_projectiles/touch`

## Inheritance

*   **`InheritTransformComponent`**: Indicates that the projectile inherits transform properties, likely from its creator.

## Tags

*   **`projectile_player`**: Identifies this entity as a player-created projectile.