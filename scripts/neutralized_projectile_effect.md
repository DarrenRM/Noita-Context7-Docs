---
title: Neutralized Projectile Effect
category: scripts
---

# Neutralized Projectile Effect

This script defines the behavior for a projectile that is "neutralized." When a projectile is neutralized, it spawns a particle effect and is then destroyed.

## Core Functionality

The primary function `shot( projectile_id )` handles the neutralization process.

### Key Actions:

*   **Get Position:** Retrieves the current position (`px`, `py`) of the projectile.
*   **Spawn Particle Effect:** Loads and spawns the `neutralized.xml` particle effect at the projectile's location.
*   **Destroy Projectile:** Immediately kills the projectile entity.

## Configuration

The script relies on an external XML file for the visual particle effect.

### `data/entities/particles/neutralized.xml`

This file (not provided in the source) would define the visual appearance and behavior of the neutralization particle effect. It typically includes:

*   **Visuals:** Sprite definitions, animations, and color.
*   **Physics:** How the particles interact with the environment.
*   **Lifetime:** How long the particles persist.
*   **Emitting Behavior:** How particles are generated and spread.

## Example Usage (Conceptual)

This script is likely called by other projectile scripts when a specific condition is met, such as hitting a certain type of enemy or interacting with a specific spell component.

```lua
-- Example of how another script might call this:
-- if (should_neutralize) then
--     dofile_once("data/scripts/projectiles/neutralized.lua")
--     shot(projectile_id)
-- end
```