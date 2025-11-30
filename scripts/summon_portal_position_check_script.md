---
title: Summon Portal Position Check Script
category: scripts
---

---

# Summon Portal Position Check Script

This script is responsible for determining the correct position to spawn a "summon portal" projectile. It checks for existing portals and ensures the new portal is spawned at a suitable distance from the player.

## Key Functionality

*   **Proximity Check:** Verifies if another "stable_portal" entity already exists within a specified radius. If one is found, the script terminates to prevent multiple portals.
*   **Portal Placement:** Calculates the optimal position for the new portal using `get_portal_position()`.
*   **Spawn Condition:** Spawns the `summon_portal_teleport.xml` entity only if the calculated portal position is within a certain radius of the current entity's position.
*   **Music Event:** Triggers a music fade-out and then plays a specific music event (`music/oneshot/dark_02`) upon successful portal spawning.

## Key Attributes & Variables

| Attribute/Variable | Description