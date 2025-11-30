---
title: Touch Oil Projectile
category: entities
---

# Touch Oil Projectile

This entity defines a player projectile that converts materials and entities into oil upon contact.

## Key Components

### MagicConvertMaterialComponent (x2)

These components handle the material and entity conversion.

*   **`from_any_material="1"`**: Allows conversion of any material.
*   **`to_material="oil"`**: Specifies that the target material is oil.
*   **`steps_per_frame`**: Controls the intensity/speed of conversion.
    *   First component: `7`
    *   Second component: `4`
*   **`loop="0"`**: Conversion happens only once.
*   **`is_circle="1"`**: Conversion area is circular.
*   **`radius`**: The radius of the conversion area.
    *   First component: `30`
    *   Second component: `20`
*   **`convert_entities="1"`**: The second component also converts entities.

### LifetimeComponent

*   **`lifetime="4"`**: The projectile exists for 4 frames.

### AudioComponent

*   **`file="data/audio/Desktop/projectiles.bank"`**: Specifies the audio bank.
*   **`event_root="player_projectiles/touch"`**: The root event for projectile touch sounds.