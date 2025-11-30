---
title: High Gravity Perk
category: scripts/perks
---

# High Gravity Perk

This script implements the "High Gravity" perk in Noita. When a player picks up this perk, it applies a gravity modification to specific entities.

## Functionality

The perk targets entities with the "homing_target" tag. For each such entity that does not already have the "high_gravity" tag:

1.  **Gravity Modification:**
    *   It modifies the `pixel_gravity` of the `CharacterPlatformingComponent` by multiplying it by 1.4.
    *   It modifies the `gravity` of the `WormComponent` by multiplying it by 1.4.
2.  **Tagging:**
    *   The "high_gravity" tag is added to the entity to prevent repeated modifications.

## Key Components Modified

*   `CharacterPlatformingComponent`: Affects general character movement and physics.
*   `WormComponent`: Specifically targets and modifies the gravity experienced by worms.

## Script Logic

The script first retrieves all entities with the "homing_target" tag. It then iterates through these entities, checking if they have already been affected by the "high_gravity" perk. If not, it applies the gravity modifications and adds the "high_gravity" tag.