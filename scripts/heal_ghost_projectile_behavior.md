---
title: Heal Ghost Projectile Behavior
category: scripts
---

---

# Heal Ghost Projectile Behavior

This script defines the behavior for a "Heal Ghost" entity in Noita, specifically its projectile firing logic. The ghost targets nearby injured allies and fires a healing projectile.

## Key Attributes

### Targeting and Range
- **`range`**: Defines the maximum distance (in pixels) the ghost will search for targets.
  - Value: `160`

### Projectile Properties
- **`projectile_velocity`**: The speed at which the healing projectile travels.
  - Value: `400`
- **`scatter`**: Controls the randomness in the projectile's trajectory, making it less predictable.
  - Value: `0.1`

### Target Selection Logic
The ghost prioritizes targets based on the following criteria:
1.  **Proximity**: It searches for entities within the defined `range`.
2.  **Tag**: Targets must have the `"mortal"` tag.
3.  **Genome Data**: Targets must possess `GenomeDataComponent`.
4.  **Herd Relation**: Targets must be considered allies (herd relation > 90).
5.  **Health Status**: Targets must be injured (current HP < max HP).

### Line of Sight (LOS) Check
- The script performs a `RaytraceSurfacesAndLiquiform` check to ensure there are no obstacles between the ghost and its target before firing. If LOS is blocked, the ghost will not shoot.

### Projectile Firing
- **`shoot_projectile`**: This function is used to spawn the healing projectile.
  - Projectile XML: `data/entities/projectiles/deck/heal_bullet_weak.xml`
  - Origin: The ghost's current position.
  - Velocity: Calculated based on the direction to the target, with added scatter.

### Firing Delay
- **`execute_every_n_frame`**: The script dynamically sets a delay for subsequent shots to prevent multiple ghosts from firing simultaneously.
  - Base Delay: `70` frames.
  - Random Variation: An additional `0` to `2` frames are added randomly.