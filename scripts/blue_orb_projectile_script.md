---
title: Blue Orb Projectile Script
category: scripts
---

---

# Blue Orb Projectile Script

This script defines the behavior of the "Blue Orb" projectile in Noita. It primarily modifies the projectile's velocity to create a specific movement pattern.

## Key Attributes

### Velocity Modification

The core functionality of this script lies in its manipulation of the projectile's velocity.

*   **`edit_component( entity_id, "VelocityComponent", function(comp,vars) ... end)`**: This targets the `VelocityComponent` of the projectile entity.
*   **`local vel_x,vel_y = ComponentGetValueVector2( comp, "mVelocity")`**: Retrieves the current velocity components of the projectile.
*   **`local angle = 0 - math.atan2(vel_y,vel_x)`**: Calculates the current angle of the projectile's velocity.
*   **`angle = angle + math.rad(10)`**: Adds a 10-degree offset to the projectile's current angle. This is the primary factor influencing the "blue orb" effect.
*   **`vel_x = math.cos(angle) * 150`**: Recalculates the X-component of the velocity based on the new angle and a magnitude of 150.
*   **`vel_y = 0-math.sin(angle) * 150`**: Recalculates the Y-component of the velocity based on the new angle and a magnitude of 150.
*   **`ComponentSetValueVector2( comp, "mVelocity", vel_x, vel_y)`**: Applies the newly calculated velocity to the projectile.

This script effectively causes the blue orb to slightly curve or change its trajectory by a fixed amount (10 degrees) in a specific direction relative to its current movement.