---
title: Touch Piss Projectile
category: entities
---

# Touch Piss Projectile

This entity defines a player projectile that converts materials and entities into "urine" upon contact.

## Key Components

### MagicConvertMaterialComponent (x2)

This component handles the material conversion. The projectile has two instances, likely for different conversion radii or step counts.

*   **`from_any_material`**: `1` (Converts any material)
*   **`to_material`**: `"urine"` (The target material)
*   **`steps_per_frame`**: Controls the intensity/speed of conversion.
    *   First instance: `4`
    *   Second instance: `7`
*   **`loop`**: `0` (Conversion happens once)
*   **`is_circle`**: `1` (Conversion area is circular)
*   **`radius`**: The area of effect for conversion.
    *   First instance: `30`
    *   Second instance: `40`
*   **`convert_entities`**: `1` (In the second instance, also converts entities)

### LifetimeComponent

*   **`lifetime`**: `6` (The projectile exists for 6 frames)

### AudioComponent

*   **`file`**: `"data/audio/Desktop/projectiles.bank"`
*   **`event_root`**: `"player_projectiles/touch"` (Plays a "touch" sound from the player projectiles bank)