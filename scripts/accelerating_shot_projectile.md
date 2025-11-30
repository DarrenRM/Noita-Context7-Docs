---
title: Accelerating Shot Projectile
category: scripts
---

---

# Accelerating Shot Projectile

This script modifies the `VelocityComponent` of a projectile, specifically reducing its `air_friction` to make it accelerate over time.

## Key Attributes

*   **`air_friction`**: This is the primary attribute modified by the script. It's reduced by 3, causing the projectile to lose less velocity to air resistance and thus accelerate.

## How it Works

1.  **Get Entity ID**: The script first obtains the `entity_id` of the projectile.
2.  **Determine Target**: It identifies the `target_id`. If the projectile has a parent (e.g., fired by a wand), the parent is used as the target. Otherwise, the projectile itself is the target.
3.  **Access Projectile Component**: It checks if the `target_id` has a `ProjectileComponent`. If not, the script exits.
4.  **Modify Velocity Component**: If a `ProjectileComponent` exists, the script accesses the `VelocityComponent` of the `target_id`.
5.  **Reduce Air Friction**: It reads the current `air_friction` value, subtracts 3 from it, and updates the `air_friction` in the `VelocityComponent`.

## Example Usage (Conceptual)

This script would typically be attached to a projectile entity. When the projectile is spawned, this script runs, and the projectile will begin to accelerate due to the reduced air friction.

```lua
-- Example of how this script might be referenced in a projectile definition
-- (This is illustrative and not part of the provided script)

-- In a projectile .xml file:
-- <Entity tags="projectile">
--     <ProjectileComponent
--         damage="5"
--         speed="20"
--         lifetime="5"
--         knockback="1"
--         explosion_radius="0"
--         on_hit_particle_emitter="data/particles/hit_effect.xml"
--         on_hit_sound="data/audio/hit.ogg"
--     />
--     <VelocityComponent
--         speed="20"
--         air_friction="10" -- Initial air friction
--     />
--     <ScriptComponent
--         script_filename="data/scripts/projectiles/accelerating_shot.lua"
--     />
-- </Entity>
```