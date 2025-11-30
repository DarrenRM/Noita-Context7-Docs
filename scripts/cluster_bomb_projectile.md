---
title: Cluster Bomb Projectile
category: scripts
---

---

# Cluster Bomb Projectile

This script defines the behavior of a cluster bomb projectile in Noita. When the projectile's velocity drops below a certain threshold, it detonates and releases a spread of smaller projectiles.

## Key Attributes and Behavior

### Projectile Detonation

-   **Velocity Threshold:** The projectile detonates when its speed falls below `50`.
-   **Detonation Trigger:** The `if ( speed < 50 )` block handles the detonation logic.

### Cluster Projectile Generation

-   **Number of Projectiles:** `how_many = 8` smaller projectiles are spawned.
-   **Angular Distribution:** The projectiles are spread evenly in a circle.
    -   `angle_inc = (math.pi * 2) / how_many` calculates the angular increment between each projectile.
-   **Projectile Type:** The spawned projectiles are of type `data/entities/projectiles/deck/grenade_small.xml`.
-   **Spawn Offset:** A small offset (`0.05`) is applied to the spawn position to prevent immediate self-collision.

### Velocity Calculation

-   The script retrieves the current velocity of the projectile using `edit_component` and `ComponentGetValueVector2`.
-   The speed is calculated using the Pythagorean theorem: `speed = math.sqrt( vel_y ^ 2 + vel_x ^ 2 )`.

### Projectile Spawning Function

-   `shoot_projectile_from_projectile` is the core function used to spawn the cluster projectiles. It takes the following arguments:
    -   `entity_id`: The ID of the parent projectile.
    -   `projectile_xml_path`: The path to the XML file defining the spawned projectile.
    -   `spawn_x`, `spawn_y`: The coordinates where the new projectile will be spawned.
    -   `vel_x`, `vel_y`: The initial velocity of the spawned projectile.
    -   `is_enemy`: A boolean indicating if the projectile is from an enemy (not used in this specific cluster logic).

### Potential Modifications

-   **Number of Projectiles:** Adjust `how_many` to change the density of the cluster.
-   **Projectile Type:** Modify `"data/entities/projectiles/deck/grenade_small.xml"` to spawn different types of projectiles.
-   **Spread Angle/Velocity:** Alter `angle_inc` and the velocity multiplier (`150`) to change the spread pattern and speed of the spawned projectiles.
-   **Detonation Threshold:** Modify the `50` value in the `if` condition to change when the cluster detonates.