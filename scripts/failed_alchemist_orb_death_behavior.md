---
title: Failed Alchemist Orb Death Behavior
category: scripts
---

# Failed Alchemist Orb Death Behavior

This script defines the behavior of the Failed Alchemist Orb when it dies, specifically the projectiles it spawns and the sound it plays.

## Key Attributes

*   **`death( damage_type_bit_field, damage_message, entity_thats_responsible, drop_items )`**: The main function triggered upon the entity's death.

## Projectile Spawning

When the orb dies, it spawns multiple projectiles in a circular pattern.

*   **`how_many`**: The number of projectiles to spawn. Set to `8.0`.
*   **`speed`**: The velocity of each projectile. Set to `500`.
*   **`angle`**: The initial random angle for the first projectile.
*   **`angle_inc`**: The increment between angles for subsequent projectiles, ensuring an even distribution.
*   **`shoot_projectile( entity_id, projectile_xml_path, pos_x, pos_y, vel_x, vel_y )`**: This function is called for each projectile.
    *   **`projectile_xml_path`**: Specifies the projectile to be spawned, which is `"data/entities/projectiles/darkflame.xml"`.

## Sound Effect

A specific sound is played upon the orb's death.

*   **`GamePlaySound( bank, sound_name, pos_x, pos_y )`**: Plays the death sound.
    *   **`bank`**: `"data/audio/Desktop/animals.bank"`
    *   **`sound_name`**: `"animals/failed_alchemist_b_orb/explode"`