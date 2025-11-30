---
title: Homing Cursor Projectile
category: scripts
---

---

# Homing Cursor Projectile

This script defines the behavior for a projectile that attempts to home in on the wand that fired it.

## Key Components and Logic

### Projectile Behavior

The core functionality revolves around adjusting the projectile's velocity to steer it towards the shooter's wand.

*   **Homing Mechanism:** The projectile calculates the difference between its current direction and the direction of the wand that fired it. It then applies a portion of this difference to its own velocity, causing it to curve.
*   **Steering Factor:** The `delta * 0.2` value controls how aggressively the projectile turns. A higher value will result in sharper turns.
*   **Velocity Adjustment:** The projectile's velocity is recalculated based on the new direction and its original speed.

### Shooter Identification

The script first identifies the entity that shot the projectile.

*   **`GetUpdatedEntityID()`:** Retrieves the ID of the projectile entity.
*   **`EntityGetFirstComponent( entity_id, "ProjectileComponent" )`:** Finds the projectile component to access shooter information.
*   **`ComponentGetValue2( comp2, "mWhoShot" )`:** Retrieves the entity ID of the projectile's shooter.

### Wand Identification

If a shooter is found, the script attempts to locate the wand they are holding.

*   **`find_the_wand_held( shooter )`:** A utility function (assumed to be defined elsewhere) that returns the ID of the wand held by the `shooter` entity.

### Direction Calculation

The script determines the target direction for homing.

*   **`EntityGetTransform( wand_id )`:** Retrieves the position and direction of the wand.
*   **`dir = 0 - math.atan2( py, px )`:** Calculates the initial direction of the wand relative to the projectile's origin (this part of the logic might be simplified or intended to be relative to the wand's position, further investigation of `find_the_wand_held` and its return values would clarify this).
*   **`dir = 0 - dir`:** Inverts the calculated wand direction.

### Velocity Component Modification

The `edit_component` function is used to modify the projectile's `VelocityComponent`.

*   **`ComponentGetValueVector2( comp, "mVelocity")`:** Gets the current velocity vector.
*   **`math.atan2( vel_y, vel_x )`:** Calculates the current direction of the projectile.
*   **`math.atan2( math.sin( dir - dir2 ), math.cos( dir - dir2 ) )`:** Calculates the angular difference between the projectile's current direction and the target wand direction.
*   **`newdir = dir2 + delta * 0.2`:** Calculates the new direction for the projectile, incorporating the steering factor.
*   **`math.cos( newdir ) * dist` and `0 - math.sin( newdir ) * dist`:** Recalculates the velocity components based on the new direction and original speed.
*   **`ComponentSetValueVector2( comp, "mVelocity", vel_x, vel_y)`:** Updates the projectile's velocity.