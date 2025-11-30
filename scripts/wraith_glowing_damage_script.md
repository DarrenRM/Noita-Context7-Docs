---
title: Wraith Glowing Damage Script
category: scripts
---

---

# Wraith Glowing Damage Script

This script defines the behavior when a "glowing wraith" entity receives damage. It triggers a visual and projectile-based response.

## Key Functionality

The primary function is `damage_received`, which is called when the entity takes damage.

### `damage_received( damage, desc, entity_who_caused, is_fatal )`

This function handles the entity's reaction to taking damage.

*   **`damage`**: The amount of damage received.
*   **`desc`**: A description of the damage.
*   **`entity_who_caused`**: The entity that inflicted the damage.
*   **`is_fatal`**: A boolean indicating if the damage is fatal.

### Core Logic

1.  **Self-Damage Prevention**: The script checks if the damage was caused by the entity itself and returns if so.
2.  **Frame Delay**: A short delay (`script_wait_frames`) is implemented to prevent rapid firing.
3.  **Random Seed**: A random seed is set based on game frame and entity position for varied behavior.
4.  **Projectile Targeting**:
    *   If the damage source (`entity_who_caused`) is valid, the script calculates the angle towards the source.
    *   If the damage source is invalid or `NULL_ENTITY`, a random angle is chosen.
5.  **Projectile Firing**:
    *   The script fires two projectiles (`wraith_glowing_laser.xml`).
    *   The angle of these projectiles is either directed towards the damage source with slight variation or completely random.
    *   A fixed `length` (400) influences the initial velocity of the projectiles.
6.  **Sound Effect**: A "shoot" sound effect is played on the entity.

## Key Attributes/Elements

*   **Projectile Type**: `data/entities/projectiles/wraith_glowing_laser.xml`
*   **Number of Projectiles**: 2
*   **Velocity Magnitude**: 400
*   **Angle Calculation**: Based on damage source or random.
*   **Sound Effect**: "shoot"
*   **Frame Delay**: 2 frames