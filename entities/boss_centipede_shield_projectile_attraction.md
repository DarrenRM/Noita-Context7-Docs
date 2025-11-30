---
title: Boss Centipede Shield Projectile Attraction
category: entities
---

# Boss Centipede Shield Projectile Attraction

This script governs the behavior of the Boss Centipede's shield, specifically its ability to attract and manipulate projectiles.

## Core Functionality

The primary function of this script is to create a gravitational pull that draws nearby projectiles towards the boss. It also modifies projectile behavior upon entering the shield's influence.

### Key Attributes and Elements

*   **`distance_full`**: Defines the radius (in pixels) within which projectiles are affected by the shield's attraction.
*   **`gravity_coeff`**: Determines the strength of the gravitational pull. A higher value results in a stronger attraction.
*   **`conversion_velocity_mult`**: A multiplier applied to the projectile's velocity when it's first converted by the shield, effectively slowing it down as it enters the field.
*   **`orbcount`**: A variable that influences the shield's behavior, particularly its ability to convert damage fields. A higher `orbcount` (presumably related to the boss's state or power) enables this conversion.

## Projectile Interaction Logic

The script iterates through all projectiles within the `distance_full` radius. For each projectile, it performs the following checks and actions:

### Projectile Attraction and Velocity Modification

1.  **Distance Calculation**: Calculates the distance between the boss and the projectile.
2.  **Direction Determination**: Determines the direction vector from the projectile to the boss.
3.  **Gravity Application**:
    *   Calculates a `gravity_percent` based on the projectile's distance from the center of the shield. Projectiles closer to the center experience a stronger pull.
    *   Applies an offset velocity (`offset_x`, `offset_y`) to the projectile, pulling it towards the boss.
    *   If the projectile is not yet "converted," its velocity is reduced by `conversion_velocity_mult`.
4.  **Velocity Component Update**: If the projectile has a `VelocityComponent`, its `mVelocity` is updated with the calculated offset.
5.  **Physics Force Application**: If no `VelocityComponent` is found, a small physics force is applied to move the projectile.

### Projectile Conversion and Behavior Changes

When a projectile is attracted for the first time (i.e., it doesn't have the `projectile_converted` tag):

1.  **Sound Effect**: Plays a "suck\_projectile" sound effect.
2.  **Collision Prevention**:
    *   The projectile's `mWhoShot` and `mShooterHerdId` are set to the boss's ID and herd ID, respectively.
    *   `friendly_fire` is set to `false`.
    *   `collide_with_shooter_frames` is set to `-1` to prevent the projectile from colliding with the boss.
3.  **Visual Effect**: Loads a trail effect (`boss_centipede_shield_trail_effect.xml`) onto the projectile.
4.  **Damage Field Conversion**:
    *   If `orbcount` is 6 or higher, any `AreaDamageComponent` on the projectile is modified to only affect the `player_unit`.
5.  **Tagging**: The `projectile_converted` tag is added to the projectile, indicating it has been processed by the shield.

### Lifetime Extension

The script also extends the lifetime of attracted projectiles by adding 2 frames to their existing `lifetime` value. This ensures they remain active within the shield's influence for a longer duration.

```lua
-- Example of how velocity is modified
local vel_x,vel_y = ComponentGetValue2( velocitycomp, "mVelocity")
vel_x = vel_x + offset_x
vel_y = vel_y + offset_y
ComponentSetValue2( velocitycomp, "mVelocity", vel_x, vel_y)

-- Example of damage component modification
for _,comp in ipairs(EntityGetComponent(id, "AreaDamageComponent") or {}) do
	ComponentSetValue2(comp, "entities_with_tag", "player_unit")
end
```