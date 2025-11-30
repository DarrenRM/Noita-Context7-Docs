---
title: Food Clock Perk Logic
category: scripts
---

# Food Clock Perk Logic

This script defines the behavior of the "Food Clock" perk in Noita, which causes the player to take damage when their hunger level drops too low.

## Core Functionality

The script monitors the player's "satiation" (hunger) level and inflicts damage when it falls below certain thresholds.

### Key Attributes

*   **`damage_starts_at_satiation_percent`**: The hunger percentage at which the player begins to take damage. (Default: `0.25` or 25%)
*   **`damage_warning_starts_at_satiation_percent`**: The hunger percentage at which a visual warning (icon flash) is triggered. (Default: `0.27` or 27%)

## Script Breakdown

The script performs the following actions:

1.  **Get Player Entity and Ingestion Component**: It retrieves the player's entity ID and its associated `IngestionComponent`, which manages hunger.
2.  **Check for Ingestion Component**: If the `IngestionComponent` exists, the script proceeds.
3.  **Monitor Satiation Levels**:
    *   It reads the current `ingestion_size` (current hunger) and `ingestion_capacity` (maximum hunger).
    *   If `count` (current hunger) is below `count_max * damage_warning_starts_at_satiation_percent`, the `m_damage_effect_lifetime` of the `IngestionComponent` is set to `2` to trigger a visual warning.
    *   If `count` is below `count_max * damage_starts_at_satiation_percent`, the player starts taking damage.
4.  **Inflict Damage**:
    *   It calculates the damage amount based on the player's maximum HP, divided by a factor (effectively `max_hp / 140`).
    *   If the player's current HP is greater than the calculated damage, the `EntityInflictDamage` function is called to apply damage.
    *   The damage type is `DAMAGE_CURSE`, the damage reason is `"$damage_hunger"`, and the source is the player's entity ID.

## Relevant Components

*   **`IngestionComponent`**: Manages the player's hunger and satiation levels.
    *   `ingestion_size`: Current hunger level.
    *   `ingestion_capacity`: Maximum hunger level.
    *   `m_damage_effect_lifetime`: Controls the duration of visual damage effects (used here for hunger warning).
*   **`DamageModelComponent`**: Manages the player's health and damage application.
    *   `max_hp`: Maximum health points.
    *   `hp`: Current health points.