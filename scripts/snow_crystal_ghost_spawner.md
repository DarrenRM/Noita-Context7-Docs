---
title: Snow Crystal Ghost Spawner
category: scripts
---

---

# Snow Crystal Ghost Spawner

This script defines the behavior for spawning "ghost" entities when a Snow Crystal building is interacted with. It aims to create an illusionary enemy near the player.

## Key Functionality

The core logic is within the `spawn_ghost()` function.

### Entity Selection

*   **`opts` table:** Contains a list of potential enemy entity filenames to spawn. These are illusionary versions of existing enemies.
    *   `"acidshooter"`
    *   `"worm_big"`
    *   `"scavenger_grenade"`
    *   `"scavenger_mine"`
    *   `"enlightened_alchemist"`
    *   `"shaman"`
    *   `"tank"`
    *   `"wizard_swapper"`

### Spawn Location Logic

The script attempts to find a suitable spawn location near the player, avoiding immediate proximity and solid surfaces.

1.  **Player Proximity Check:** It first checks if a player is within a `max_radius` (512 units).
2.  **Random Offset:** If a player is found, it generates random `dx` and `dy` coordinates relative to the player's position, within a range of -200 to 200.
3.  **Distance and Wall Check Loop:**
    *   It enters a `while` loop that continues as long as the calculated spawn point is too close to the player (`dist < 100`) or if a `wall` is detected.
    *   The loop has a `limit` of 20 iterations to prevent infinite loops.
    *   **Raycasting:** Inside the loop, `RaytraceSurfaces` is used to check for walls. It performs `raycasts` (4 by default) in different directions from the potential spawn point. If any raycast hits a surface, `wall` is set to `true`, and the loop breaks to try a new location.
4.  **Spawn:** Once a suitable location is found (sufficiently far from the player and not inside a wall), a blue `poof_blue.xml` particle effect is spawned, followed by the chosen illusionary enemy entity.

### Initialization

*   The `spawn_ghost()` function is called directly at the end of the script to execute the spawning logic when the script is loaded.