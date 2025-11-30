---
title: Glass Cannon Enemy Perk
category: scripts
---

---

# Glass Cannon Enemy Perk

This script modifies projectile and explosion damage for entities that possess it, significantly increasing their offensive capabilities at the cost of survivability.

## Key Functionality

The `shot` function is the core of this perk. When an entity with this perk fires a projectile, this function is triggered to amplify its damage.

### Damage Amplification

*   **Base Projectile Damage:** Multiplied by `3.0`.
*   **Damage by Type:** All listed damage types (e.g., `projectile`, `explosion`, `fire`) are also multiplied by `3.0`.
*   **Explosion Configuration:** Various explosion-related parameters are amplified by `4.0`.

### Affected Parameters

The script targets and modifies the following components and their associated values:

#### Projectile Component Modifications

*   `damage`: Base damage of the projectile.
*   `damage_by_type`: Specific damage types applied by the projectile.
    *   `projectile`
    *   `explosion`
    *   `melee`
    *   `ice`
    *   `slice`
    *   `electricity`
    *   `radioactive`
    *   `drill`
    *   `fire`

#### Explosion Configuration Modifications

*   `config_explosion`: Parameters related to the explosion effect.
    *   `explosion_radius`
    *   `ray_energy`
    *   `sparks_count_max`
    *   `camera_shake`
    *   `damage` (within explosion config)
    *   `material_sparks_count_max`
    *   `physics_explosion_power.max`
    *   `stains_radius`