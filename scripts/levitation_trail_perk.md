---
title: Levitation Trail Perk
category: scripts
---

---

# Levitation Trail Perk

This script defines the behavior for the "Levitation Trail" perk in Noita. When the player activates their jetpack, this perk spawns a projectile that follows them, creating a visual trail.

## Key Functionality

*   **Trigger:** The perk activates when the player's jetpack is emitting (indicated by `mJetpackEmitting` being greater than 0).
*   **Projectile Spawning:** It spawns a projectile of type `data/entities/projectiles/levitation_trail.xml`.
*   **Velocity Calculation:** The spawned projectile inherits a modified velocity based on the player's current velocity, with specific multipliers for X and Y axes.

## Core Components

### CharacterPlatformingComponent

This component is essential for detecting jetpack usage. The script checks if the player has this component and if the `mJetpackEmitting` value is active.

### Projectile Spawning

The `shoot_projectile` function is used to create the levitation trail projectile.

```lua
shoot_projectile( entity_id, "data/entities/projectiles/levitation_trail.xml", pos_x, pos_y, vel_x, vel_y )
```

*   `entity_id`: The ID of the entity that triggered the perk (the player).
*   `"data/entities/projectiles/levitation_trail.xml"`: The XML file defining the levitation trail projectile.
*   `pos_x`, `pos_y`: The current position of the player.
*   `vel_x`, `vel_y`: The calculated velocity for the spawned projectile.

## Velocity Modification

The velocity of the spawned projectile is derived from the player's current velocity, but with specific scaling:

*   **X-axis:** `vel_x = -vel_x * 75` (Reversed and scaled by 75)
*   **Y-axis:** `vel_y = -vel_y * 50` (Reversed and scaled by 50)

This creates a trailing effect that moves with the player but with a slight delay and directional influence.