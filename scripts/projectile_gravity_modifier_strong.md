---
title: Projectile Gravity Modifier (Strong)
category: scripts
---

---

# Projectile Gravity Modifier (Strong)

This script modifies the behavior of nearby projectiles, applying a strong gravitational pull towards the entity executing this script. It's designed to create a localized gravity well that affects other projectiles within a certain range.

## Key Functionality

This script iterates through all entities tagged as "projectile" and applies a directional force to them based on their proximity to the entity executing this script.

### Core Mechanics

*   **Proximity Detection:** The script calculates the Manhattan distance and then the Euclidean distance to nearby projectiles.
*   **Gravity Application:** A gravitational force is applied to projectiles within a `distance_full` range. The strength of this force is inversely proportional to the projectile's distance.
*   **Directional Force:** The force is applied in the direction pointing from the projectile towards the entity executing the script.
*   **Velocity Modification:** The script directly modifies the `mVelocity` of the `VelocityComponent` of affected projectiles.

## Key Attributes and Variables

| Attribute/Variable | Description