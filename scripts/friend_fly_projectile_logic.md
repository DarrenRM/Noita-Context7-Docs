---
title: Friend Fly Projectile Logic
category: scripts
---

# Friend Fly Projectile Logic

This script defines the behavior for the "Friend Fly" projectile in Noita. It primarily focuses on its homing capabilities and target acquisition.

## Key Components and Behavior

### Projectile Initialization

*   **Entity ID and Transform:** Retrieves the projectile's unique ID and its current position (`x`, `y`).
*   **Targeting Variables:** Initializes `target_id` and `targetstorage` to track the projectile's target.
*   **Radius:** Sets a `radius` of 64, likely used for proximity checks.
*   **Owner Identification:** Retrieves the `home_id` (the entity that shot the projectile) using `ProjectileComponent.mWhoShot`.

### Sprite Orientation

*   The script adjusts the `special_scale_x` of the `SpriteComponent` based on the projectile's horizontal velocity (`vel_x`).
    *   If `vel_x > 0`, the sprite is scaled to face right (`special_scale_x = 1`).
    *   If `vel_x < 0`, the sprite is scaled to face left (`special_scale_x = -1`).

### Homing and Target Management

This is the core logic of the script. It handles how the projectile finds and maintains its target.

#### Target Acquisition and Re-evaluation

1.  **Owner Check:** The script proceeds only if the `home_id` is valid (not `nil` or `NULL_ENTITY`).
2.  **Owner Position:** Retrieves the owner's position (`px`, `py`). If the owner's position cannot be determined, the projectile is killed.
3.  **Variable Storage:** It searches for a `VariableStorageComponent` named "target" to retrieve the current `target_id` and its storage component.
4.  **Target Validity Check:**
    *   Calculates the distance between the projectile and its owner (`hdist`).
    *   If a `target_id` is already set:
        *   It retrieves the target's position (`tx`, `ty`).
        *   If the target is no longer valid (e.g., destroyed, or too far away from both the projectile and its owner), the `target_id` is reset to `0`, and the `HomingComponent` is configured to target the shooter (`target_who_shot = true`).
    *   If no `target_id` is set:
        *   It searches for entities with the tag "mortal" within a `radius` around the owner's position.
        *   The first valid "mortal" entity that is not the projectile itself or its owner is selected as the new `target_id`.
        *   The `HomingComponent` is updated to target this specific entity (`predefined_target = target_id`, `target_who_shot = false`).
        *   The `target_id` is stored in the `VariableStorageComponent`.

#### Target Distance Thresholds

*   **Projectile-Owner Distance:** If `hdist` exceeds `radius * 2.5`, the target is considered lost.
*   **Target-Projectile Distance:** If the distance between the target and the projectile (`dist`) exceeds `radius * 2`, the target is considered lost.
*   **Target-Owner Distance:** If the distance between the target and the owner (`hdist2`) exceeds `radius * 3`, the target is considered lost.

### Target Reset Logic

If any of the target validity checks fail, the `target_id` is reset to `0`, and the `HomingComponent` is reconfigured to target the shooter.

### Projectile Destruction

If the owner's position cannot be determined, the projectile is destroyed using `EntityKill( entity_id )`.