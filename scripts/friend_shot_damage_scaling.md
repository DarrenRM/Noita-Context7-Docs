---
title: Friend Shot Damage Scaling
category: scripts
---

# Friend Shot Damage Scaling

This script modifies the damage and explosion properties of projectiles fired by "friendly" entities (e.g., summons, companions) based on a global kill counter.

## Core Functionality

The `shot` function is designed to be called when a projectile is fired. It checks a global variable `ULTIMATE_KILLER_KILLS` and, if its value is greater than zero, scales the projectile's damage and explosion parameters.

### Key Attributes Modified:

*   **`damage`**: The base damage of the projectile.
*   **`config_explosion.damage`**: The damage dealt by any explosion associated with the projectile.
*   **`config_explosion.explosion_radius`**: The radius of the explosion.

## Scaling Logic

The scaling is directly proportional to the value of `ULTIMATE_KILLER_KILLS`.

*   **Damage Increase**: `tcount * 0.25`
*   **Explosion Damage Increase**: `tcount * 0.5`
*   **Explosion Radius Increase**: `tcount * 2`

Where `tcount` is the current value of `ULTIMATE_KILLER_KILLS`.

## Global Variable Dependency

*   **`ULTIMATE_KILLER_KILLS`**: A global variable that tracks the number of kills. This script assumes this variable is managed elsewhere in the game's logic.

## Usage

This script is intended to be integrated into the projectile firing mechanism of friendly entities. When a friendly entity fires a projectile, this `shot` function should be called with the projectile's entity ID.