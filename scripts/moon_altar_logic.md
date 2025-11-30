---
title: Moon Altar Logic
category: scripts
---

# Moon Altar Logic

This script defines the behavior of the Moon Altar entity in Noita, handling interactions with player essences and celestial bodies to trigger special events and unlock content.

## Core Functionality

The Moon Altar acts as a trigger for several distinct events based on the player's collected essences and proximity to specific celestial entities.

### Essence-Based Activation

The primary activation requires the player to possess specific essences and be within a certain range of the altar.

*   **Required Essences:**
    *   `essence_fire`
    *   `essence_air`
    *   `essence_water`
    *   `essence_laser`
*   **Exclusion Conditions:**
    *   The player must *not* have the flag `u_dheglmticg` (likely a specific player state or debuff).
    *   No "seed\_e" entities (likely related to the sun) should be nearby.
    *   No "seed\_f" entities (likely related to a dark sun) should be nearby.
*   **Player Proximity:** The player must be within 48 units of the altar.

### Activation Outcomes

Upon successful activation, the altar can trigger one of two effects:

1.  **Standard Activation:**
    *   Grants the persistent flag `card_unlocked_destruction`.
    *   Creates an item action entity for "DESTRUCTION".
    *   Loads `data/entities/misc/moon_effect.xml`.
    *   Displays a game message: `$log_moon_altar`, `$logdesc_moon_altar`.
    *   Grants the persistent flag `secret_moon`.
2.  **Drunk Moon Activation (if `essence_alcohol` is also present):**
    *   Grants the persistent flag `secret_moon2`.
    *   Loads `data/entities/misc/moon_effect_drunk.xml`.
    *   Displays a game message: `$log_moon_altar`, `$logdesc_moon_altar_drunk`.

After either activation, the Moon Altar entity is destroyed.

## Celestial Body Collision Logic

The altar also reacts to the presence of celestial bodies ("seed\_e" for sun, "seed\_f" for dark sun) and handles persistent flags related to their interaction.

### Collision Triggers

*   **Sun Collision:** If a "seed\_e" entity is within 56 units and the `moon_is_sun` flag is *not* persistent.
*   **Dark Sun Collision:** If a "seed\_f" entity is within 56 units and the `moon_is_darksun` flag is *not* persistent.

### Collision Outcomes

The script tracks multiple collision events using `secret_sun_collision_1` and `secret_sun_collision_2` flags.

*   **First Collision (either sun or dark sun):**
    *   Loads a `deck/explosion_giga.xml` projectile.
    *   Sets `secret_sun_collision_1` flag.
    *   **If Sun:** Loads `moon_effect_sun.xml`, removes `moon_is_darksun`, adds `moon_is_sun`.
    *   **If Dark Sun:** Loads `moon_effect_darksun.xml`, removes `moon_is_sun`, adds `moon_is_darksun`.
    *   Displays a game message: `$log_collision_1`, `$logdesc_collision_1`.
*   **Second Collision (either sun or dark sun):**
    *   Sets `secret_sun_collision_2` flag.
    *   **If Sun:** Loads `moon_effect_sun.xml`, displays `$log_collision_2`, `$logdesc_collision_2`, adds `secret_sun_collision`, removes `moon_is_darksun`, adds `moon_is_sun`.
    *   **If Dark Sun:** Loads `moon_effect_darksun.xml`, displays `$log_collision_3`, `$logdesc_collision_3`, adds `secret_darksun_collision`, removes `moon_is_sun`, adds `moon_is_darksun`.

### Special Hat Unlock

*   If both `moon_is_sun` and `darkmoon_is_darksun` are persistent, the `secret_hat` flag is added.

After any celestial body collision, the Moon Altar entity is destroyed.

## Key Variables and Flags

*   **Essence Checks:** `essence_fire`, `essence_air`, `essence_water`, `essence_laser`, `essence_alcohol`.
*   **Player/Entity Checks:** `players`, `players_` (for `u_dheglmticg` flag), `sun` (for `seed_e`), `sun2` (for `seed_f`).
*   **Persistent Flags:**
    *   `u_dheglmticg`: Used to check for a specific player state.
    *   `card_unlocked_destruction`: Unlocked on standard essence activation.
    *   `secret_moon`: Unlocked on standard essence activation.
    *   `secret_moon2`: Unlocked on drunk moon essence activation.
    *   `moon_is_sun`: Tracks if the moon has become the sun.
    *   `moon_is_darksun`: Tracks if the moon has become the dark sun.
    *   `secret_sun_collision_1`: Tracks the first celestial collision.
    *   `secret_sun_collision_2`: Tracks the second celestial collision.
    *   `secret_sun_collision`: Specific flag for sun collision.
    *   `secret_darksun_collision`: Specific flag for dark sun collision.
    *   `secret_hat`: Unlocked under specific sun/dark sun conditions.
*   **Entity Loading:** `EntityLoad` is used to spawn visual effects and items.
*   **Game Messages:** `GamePrintImportant` displays localized text to the player.