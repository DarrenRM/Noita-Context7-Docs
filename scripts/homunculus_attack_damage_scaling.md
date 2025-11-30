---
title: Homunculus Attack Damage Scaling
category: scripts
---

# Homunculus Attack Damage Scaling

This script modifies the damage of homunculus projectiles based on player progression.

## Key Functionality

The `shot` function is triggered when a homunculus projectile is fired. It dynamically adjusts the projectile's damage.

### Damage Calculation

The damage increase is determined by two main factors:

*   **Homunculus Perk Pickups:** The number of times the "PERK_PICKED_HOMUNCULUS" perk has been acquired.
*   **Holy Mountain Visits:** The total number of times the player has visited the Holy Mountain.

### Damage Formula

The additional damage applied to the projectile is calculated as follows:

```lua
local extra_damage = math.min( 50, 1.2 ^ math.max( pickup_count - 1, 0 ) ) + ( hm_visits * 0.1 )
```

This formula ensures that:

*   Damage scales exponentially with each Homunculus perk pickup, capped at a certain point.
*   A small amount of damage is added for every Holy Mountain visit.

### Conditions for Damage Modification

Damage is only modified if:

*   The projectile has a `ProjectileComponent`.
*   The projectile does *not* have the `projectile_heal` tag (meaning it's an attack projectile, not a healing one).

## Global Variables Used

*   `PERK_PICKED_HOMUNCULUS_PICKUP_COUNT`: Stores the number of times the Homunculus perk has been picked up.
*   `HOLY_MOUNTAIN_VISITS`: Stores the total number of Holy Mountain visits.