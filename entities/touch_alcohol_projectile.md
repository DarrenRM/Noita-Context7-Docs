---
title: Touch Alcohol Projectile
category: entities
---

# Touch Alcohol Projectile

This entity defines a player projectile that converts materials and entities into alcohol upon contact.

## Key Components

### MagicConvertMaterialComponent (x2)

This component handles the material conversion. The projectile has two instances, likely for different conversion radii or intensities.

*   **`from_any_material`**: `1` (Converts any material)
*   **`to_material`**: `alcohol` (Converts to alcohol)
*   **`steps_per_frame`**: Controls the speed/intensity of conversion.
    *   First instance: `4`
    *   Second instance: `7`
*   **`loop`**: `0` (Conversion happens once)
*   **`is_circle`**: `1` (Conversion area is circular)
*   **`radius`**: The area of effect for conversion.
    *   First instance: `20`
    *   Second instance: `30`
*   **`convert_entities`**: `1` (On the second instance, also converts entities)

### LifetimeComponent

*   **`lifetime`**: `4` (The projectile exists for 4 frames)

### AudioComponent

*   **`file`**: `data/audio/Desktop/projectiles.bank`
*   **`event_root`**: `player_projectiles/touch` (Plays a "touch" sound effect for player projectiles)