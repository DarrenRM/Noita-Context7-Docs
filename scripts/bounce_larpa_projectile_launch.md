---
title: Bounce Larpa Projectile Launch
category: scripts
---

# Bounce Larpa Projectile Launch

This script defines the behavior for a projectile that, upon certain conditions, launches multiple copies of itself. It's designed to be attached to a projectile entity.

## Core Functionality

The primary function of this script is to detect if the projectile it's attached to was launched with significant velocity and if it has a specific "projectile\_file" variable set. If both conditions are met, it will:

1.  **Determine the projectile to clone:** Reads the `projectile_file` variable from the closest projectile entity with the "projectile" tag.
2.  **Check for sufficient velocity:** Ensures the projectile has a combined absolute velocity greater than 50.
3.  **Launch copies:** Shoots a specified number of new projectiles, angled outwards from the original projectile's trajectory.
4.  **Tag cloned projectiles:** Adds the "projectile\_cloned" tag to the newly spawned projectiles.
5.  **Destroy original:** Kills the original projectile entity.

## Key Attributes and Elements

### Projectile Cloning Logic

*   **`projectile_file`:** A string variable that must be present in a `VariableStorageComponent` of the projectile. This variable specifies the file path of the projectile to be cloned (e.g., `"data/projectiles/larpa.xml"`).
*   **Velocity Threshold:** The script checks if the sum of the absolute values of the projectile's X and Y velocity (`math.abs( vel_x ) + math.abs( vel_y )`) is greater than `50`. If not, cloning does not occur.
*   **Number of Clones (`how_many`):** Defaults to `4`. This determines how many projectiles are spawned.
*   **Launch Angle Calculation:** The new projectiles are launched in a circular pattern around the original projectile's velocity vector. The `angle_inc` variable calculates the angular separation between each clone.
*   **Spawn Offset:** Cloned projectiles are spawned with a slight offset from the original projectile's position to prevent immediate self-collision.

### Script Components and Variables

*   **`entity_id`:** The unique identifier of the projectile entity this script is attached to.
*   **`pos_x`, `pos_y`:** The current position of the projectile.
*   **`vel_x`, `vel_y`:** The velocity components of the projectile.
*   **`test`:** A variable used to store the closest entity with the "projectile" tag.
*   **`shoot_projectile_from_projectile( entity_id, projectile_file, pos_x, pos_y, shot_vel_x, shot_vel_y, is_homing )`:** A utility function (likely from `utilities.lua`) used to spawn new projectiles from an existing projectile.
*   **`EntityAddTag( eid, "projectile_cloned" )`:** Adds a tag to the newly created projectile.
*   **`EntityKill( entity_id )`:** Destroys the current projectile entity.

### Dependencies

*   **`dofile_once("data/scripts/lib/utilities.lua")`:** This line indicates a dependency on the `utilities.lua` script, which likely contains helper functions like `shoot_projectile_from_projectile`.

---