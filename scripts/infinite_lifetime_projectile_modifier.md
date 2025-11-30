---
title: Infinite Lifetime Projectile Modifier
category: scripts
---

---

# Infinite Lifetime Projectile Modifier

This script modifies a projectile to have an infinite lifetime and allows it to collide with its shooter.

## Key Attributes Modified

The script targets the `ProjectileComponent` of an entity and applies the following modifications:

### `lifetime`
- **Value:** `-1`
- **Description:** Sets the projectile's lifetime to effectively infinite. This means the projectile will not despawn due to time.

### `friendly_fire`
- **Value:** `true`
- **Description:** Enables friendly fire for the projectile. The projectile can now damage its owner or other entities belonging to the same faction.

### `collide_with_shooter_frames`
- **Value:** `12`
- **Description:** Allows the projectile to collide with its shooter for a specified number of frames (12 frames in this case). This prevents the projectile from immediately passing through the caster.

## Usage

This script is typically applied to projectiles that are spawned by other entities. It ensures that the projectile persists indefinitely and can interact with its environment and caster in specific ways.

## Technical Details

- The script retrieves the `entity_id` and its transform.
- It then identifies the `parent_id` to determine the entity that spawned the projectile.
- If a parent is found, it attempts to access the `ProjectileComponent`.
- If the `ProjectileComponent` exists, it uses `edit_component` to modify the `lifetime`, `friendly_fire`, and `collide_with_shooter_frames` attributes.