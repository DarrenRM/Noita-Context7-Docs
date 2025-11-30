---
title: Dark Moon Altar Logic
category: scripts
---

# Dark Moon Altar Logic

This script defines the behavior of the Dark Moon Altar entity in Noita, handling its activation conditions and interactions with game states and other entities.

## Core Functionality

The Dark Moon Altar acts as a trigger for special events based on the player's collected essences and the presence of specific "sun" entities.

## Activation Conditions

The altar activates under two primary scenarios:

### 1. Dark Moon Event Activation

This occurs when the player has collected specific essences and is in close proximity to the altar.

*   **Required Essences:**
    *   `essence_fire`
    *   `essence_air`
    *   `essence_water`
    *   `essence_laser`
*   **Exclusionary Conditions:**
    *   The player must *not* have the `u_dheglmticg` flag (likely a specific player state or debuff).
    *   No "seed\_e" entity (likely a "sun" entity) should be nearby.
    *   No "seed\_f" entity (likely a "dark sun" entity) should be nearby.
*   **Player Proximity:**
    *   The player must be within a Manhattan distance of 48 units from the altar.
*   **On Activation:**
    *   Sets the persistent flag `secret_dmoon`.
    *   Spawns `data/entities/misc/moon_effect2.xml`.
    *   Displays an important game message (`$log_dark_moon_altar`, `$logdesc_dark_moon_altar`).
    *   The altar entity is destroyed.

### 2. Sun/Dark Sun Collision Event

This occurs when the altar collides with a "sun" (`seed_e`) or "dark sun" (`seed_f`) entity.

*   **Triggering Entities:**
    *   Presence of a "seed\_e" entity within 56 units.
    *   Presence of a "seed\_f" entity within 56 units.
*   **State Tracking:**
    *   The script checks and manipulates persistent flags like `darkmoon_is_sun`, `darkmoon_is_darksun`, `secret_sun_collision_1`, `secret_sun_collision_2`, `secret_sun_collision`, and `secret_darksun_collision` to manage the state of these events and prevent repeated triggers.
*   **On Collision:**
    *   Spawns `data/entities/projectiles/deck/explosion_giga.xml`.
    *   Depending on which sun entity is present, it spawns specific effects:
        *   `data/entities/misc/moon_effect_sun.xml` for "seed\_e".
        *   `data/entities/misc/moon_effect_darksun.xml` for "seed\_f".
    *   Displays important game messages related to the collision.
    *   Sets/removes persistent flags to indicate which type of sun was involved and the collision sequence.
    *   If both `moon_is_sun` and `darkmoon_is_darksun` are present, it sets `secret_hat`.
    *   The altar entity is destroyed.

## Key Variables and Flags

*   `entity_id`: The unique identifier for the Dark Moon Altar entity.
*   `x`, `y`: The coordinates of the altar.
*   `test`: A flag name (`u_dheglmticg`) used for an exclusionary condition.
*   `essence_1` to `essence_4`: Booleans indicating the presence of fire, air, water, and laser essences.
*   `players`: A list of all player entities.
*   `players_`: A list of player entities with the `u_dheglmticg` flag.
*   `sun`: Entities tagged "seed\_e" within radius.
*   `sun2`: Entities tagged "seed\_f" within radius.
*   `secret_dmoon`: Persistent flag set upon successful Dark Moon event activation.
*   `darkmoon_is_sun`: Persistent flag indicating the altar has interacted with a "sun".
*   `darkmoon_is_darksun`: Persistent flag indicating the altar has interacted with a "dark sun".
*   `secret_sun_collision_1`, `secret_sun_collision_2`: Flags to track the sequence of sun collisions.
*   `secret_sun_collision`, `secret_darksun_collision`: Flags indicating specific sun collision outcomes.
*   `secret_hat`: A flag set if both `moon_is_sun` and `darkmoon_is_darksun` are active.

## External Dependencies

*   `data/scripts/lib/utilities.lua`: Provides utility functions.
*   `data/entities/misc/moon_effect2.xml`: Effect spawned for Dark Moon event.
*   `data/entities/projectiles/deck/explosion_giga.xml`: Explosion effect for sun collisions.
*   `data/entities/misc/moon_effect_sun.xml`: Effect for sun collision.
*   `data/entities/misc/moon_effect_darksun.xml`: Effect for dark sun collision.