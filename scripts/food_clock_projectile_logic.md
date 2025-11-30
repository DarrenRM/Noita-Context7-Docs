---
title: Food Clock Projectile Logic
category: scripts
---

---

# Food Clock Projectile Logic

This script defines the behavior of the "Food Clock" projectile in Noita, specifically how it affects the player's ingestion capacity and damage.

## Core Functionality

The primary purpose of this projectile is to modify the player's "IngestionComponent" when it hits them. It calculates a percentage based on the player's current ingestion size relative to their maximum capacity and applies a damage bonus to the projectile itself, scaled by this percentage.

## Key Attributes & Logic

### Ingestion Scaling

*   **`damage_add`**: A base value (1.6) added to the projectile's damage.
*   **`count_max`**: Retrieves the player's maximum ingestion capacity.
*   **`count`**: Calculates the current "excess" ingestion size, representing how much the player has eaten beyond a certain threshold (60% of max capacity).
*   **`percent`**: Determines the percentage of excess ingestion relative to the maximum capacity. This value is then further processed.

### Percentage Transformation (`food_clock_fn`)

The `food_clock_fn` function applies a non-linear scaling to the `percent` value:

*   For values less than 10, the function returns the value directly (linear scaling).
*   For values 10 and above, it applies a logarithmic transformation: `9.549 + (math.log(1 + (x - 9) / 9) * 10)`. This means the damage bonus increases more slowly as the player's ingestion capacity becomes very high.

### Damage Application

*   **`currdamage`**: Retrieves the projectile's current damage value.
*   **`healing`**: Checks if the projectile has any "healing" damage type.
*   If the projectile is not a healing type (`healing == 0`), the projectile's damage is increased by `damage_add * percent`.

## Script Flow

1.  **Get Entity ID**: Retrieves the ID of the projectile entity.
2.  **Get Projectile Component**: Accesses the `ProjectileComponent` of the projectile.
3.  **Check Shooter**: Verifies that the projectile was shot by a player.
4.  **Get Ingestion Component**: If shot by a player, it retrieves the player's `IngestionComponent`.
5.  **Calculate Ingestion Percentage**: Determines the player's current ingestion level relative to their capacity.
6.  **Apply Percentage Transformation**: Scales the ingestion percentage using the `food_clock_fn`.
7.  **Modify Projectile Damage**: If the projectile is not a healing type, its damage is increased based on the transformed ingestion percentage.