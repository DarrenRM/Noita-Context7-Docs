---
title: Orb Projectile Script
category: scripts
---

---

# Orb Projectile Script

This script defines the behavior for a projectile that acts as an "orb." It's designed to be fired from another projectile, creating a chain reaction or secondary effect.

## Key Functionality

*   **Spawning:** The orb projectile is spawned using `shoot_projectile_from_projectile`.
*   **Movement:** The orb's velocity is calculated based on a rotating angle, causing it to move in a circular pattern over time.
*   **Sound:** A "duplicate" sound effect is played when the orb is spawned.

## Core Attributes

The script primarily focuses on the dynamic aspects of the orb's creation and initial movement. The visual and physical properties of the orb itself are defined in its associated `.xml` file (`data/entities/projectiles/orb.xml`).

### Movement Calculation

The `angle` variable determines the direction of the orb's velocity. It increases linearly with `time` (which is based on game frames), resulting in a constant rotational speed.

```lua
local time  = GameGetFrameNum() / 60.0 -- Calculate time in seconds
local angle = time * 2               -- Angle increases over time
local vel_x = math.cos(angle) * 90   -- X velocity based on cosine of angle
local vel_y = -math.sin(angle) * 90  -- Y velocity based on sine of angle (inverted for typical game Y-axis)
```

### Spawning Logic

The `shoot_projectile_from_projectile` function is crucial for this script. It takes the `entity_id` of the projectile that spawned this orb, the path to the orb's entity definition (`.xml`), and the calculated position and velocity.

```lua
shoot_projectile_from_projectile( entity_id, "data/entities/projectiles/orb.xml", pos_x, pos_y, vel_x, vel_y )
```

### Sound Effect

A specific sound is triggered upon the orb's creation.

```lua
GameEntityPlaySound( entity_id, "duplicate" )
```