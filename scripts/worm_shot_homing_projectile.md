---
title: Worm Shot Homing Projectile
category: scripts
---

---

# Worm Shot Homing Projectile

This script enables homing behavior for a projectile tagged as "worm_shot_homing".

## Core Functionality

### Entity Tagging

*   **`worm_shot_homing`**: This tag is applied to the entity, enabling the associated homing logic.

### Component Enabling

*   **`EntitySetComponentsWithTagEnabled( entity_id, "worm_shot_homing", true )`**: This function ensures that any components specifically designed to work with the "worm_shot_homing" tag are activated for the projectile. This is the primary mechanism for activating the homing behavior.

## Key Attributes (Implied by Functionality)

While the provided script is minimal, the homing functionality implies the presence of other components and configurations within the Noita engine that would handle:

*   **Target Acquisition**: Logic to detect and lock onto nearby enemies.
*   **Movement Control**: Steering mechanisms to guide the projectile towards the acquired target.
*   **Projectile Properties**: Standard projectile attributes like speed, damage, lifetime, etc., which would be defined elsewhere in the entity's configuration.