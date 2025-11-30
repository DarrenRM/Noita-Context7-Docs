---
title: Spells to Power Projectile Modifier
category: scripts
---

---

# Spells to Power Projectile Modifier

This script modifies the behavior of projectiles in Noita, specifically enhancing the "Spells to Power" spell. When cast, it seeks out other projectiles created by the same caster within a radius and absorbs their damage and explosion properties to augment the caster's own projectile.

## Core Functionality

The primary goal of this script is to:

*   **Target Identification:** Locate other projectiles within a specified radius.
*   **Caster Verification:** Ensure that the targeted projectiles were also fired by the same entity that cast the "Spells to Power" spell.
*   **Property Absorption:** Extract damage and explosion data from identified projectiles.
*   **Self-Augmentation:** Apply the absorbed damage and explosion properties to the caster's projectile, increasing its effectiveness.
*   **Visual Feedback:** Spawn particle effects to indicate the absorption and enhancement process.

## Key Attributes & Elements

### Projectile Targeting and Filtering

*   **`radius`**: Defines the search area for other projectiles.
*   **`"projectile"` tag**: Used to identify entities that are projectiles.
*   **Exclusion Tags**:
    *   `"spells_to_power_target"`: Prevents a projectile from being targeted by itself or other "Spells to Power" projectiles.
    *   `"projectile_not"`: A general tag to exclude certain projectiles from being modified.

### Property Absorption Logic

*   **`mWhoShot`**: A component value that identifies the entity that fired a projectile. This is crucial for ensuring only projectiles from the same caster are absorbed.
*   **`damage`**: The base damage value of a projectile.
*   **`config_explosion.damage`**: The damage value of an explosion associated with a projectile.
*   **`config_explosion.explosion_radius`**: The radius of an explosion.

### Augmentation Calculations

The script calculates the total absorbed damage and explosion power, then applies a multiplier to augment the caster's projectile.

*   **Damage Increase**: `damage = damage + count * 0.1`
*   **Explosion Damage Increase**: `expdamage = expdamage + expcount * 0.1`
*   **Explosion Radius Increase**: `exprad = math.min( 120, math.floor( exprad + math.log( totalcount * 10.5 ) ) )`

### Particle Effects

*   **`data/entities/particles/poof_red_tiny.xml`**: Spawned when a projectile is successfully absorbed.
*   **`data/entities/particles/tinyspark_red_large.xml`**: Spawned at the caster's projectile's location to visually represent the power-up. The number of particles emitted is dynamically calculated based on the total absorbed power.

### Component Modifications

When a projectile is targeted for absorption, several of its components are modified to prevent it from acting independently:

*   **`on_death_explode`**: Set to `false`.
*   **`on_lifetime_out_explode`**: Set to `false`.
*   **`collide_with_entities`**: Set to `false`.
*   **`collide_with_world`**: Set to `false`.
*   **`lifetime`**: Set to `999` (effectively making it last indefinitely until absorbed).
*   **`LifetimeComponent`**: Added with a `lifetime` of "1" to ensure it's quickly removed after absorption.