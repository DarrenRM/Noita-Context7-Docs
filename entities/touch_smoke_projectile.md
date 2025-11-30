---
title: Touch Smoke Projectile
category: entities
---

# Touch Smoke Projectile

This entity defines a player-created projectile that converts materials and entities into smoke upon contact.

## Key Components

### MagicConvertMaterialComponent (x2)

This component is responsible for the material conversion effect. The projectile has two instances of this component, likely for slightly different conversion behaviors or priorities.

*   **`from_any_material="1"`**: Allows conversion of any material.
*   **`to_material="smoke"`**: Specifies that the target material is smoke.
*   **`steps_per_frame`**: Controls the intensity or speed of the conversion.
    *   First instance: `steps_per_frame="6"`
    *   Second instance: `steps_per_frame="7"`
*   **`loop="0"`**: The conversion effect does not loop.
*   **`is_circle="1"`**: The conversion area is circular.
*   **`radius="30"`**: The radius of the circular conversion area.
*   **`convert_entities="1"`** (Second instance only): This instance also converts entities within its radius into smoke.

### LifetimeComponent

*   **`lifetime="4"`**: The projectile exists for 4 seconds before dissipating.

### AudioComponent

*   **`file="data/audio/Desktop/projectiles.bank"`**: Specifies the audio bank to use.
*   **`event_root="player_projectiles/touch"`**: Defines the root event for player projectile touch sounds.

## Entity Tags

*   **`projectile_player`**: Indicates that this entity is a projectile created by the player.