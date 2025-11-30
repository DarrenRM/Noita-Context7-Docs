---
title: Pollen Ball Burst Projectile
category: scripts
---

# Pollen Ball Burst Projectile

This script defines the behavior for a projectile that, upon impact or expiration, bursts into multiple smaller "pollen" projectiles and a particle effect.

## Core Functionality

*   **Spawning:** When this projectile is active, it spawns a specified number of smaller projectiles in a radial pattern.
*   **Particle Effect:** A visual particle effect is also spawned at the location of the burst.
*   **Self-Destruction:** The original projectile is destroyed after its effect.

## Key Attributes & Elements

### Projectile Spawning

*   `how_many`: Determines the number of smaller projectiles to spawn. In this case, it's set to `16`.
*   `angle_inc`: Calculates the angular separation between spawned projectiles to ensure an even distribution.
*   `length`: A random value determining the initial velocity magnitude of each spawned projectile.
*   `vel_x`, `vel_y`: Calculated velocity components for each spawned projectile based on angle and length.
*   `shoot_projectile()`: The function used to create and launch the smaller "pollen" projectiles.
    *   `entity_id`: The ID of the current projectile entity.
    *   `"data/entities/projectiles/pollen.xml"`: The XML file defining the spawned projectile type.
    *   `pos_x`, `pos_y`: The spawn position of the new projectiles (slightly offset from the burst center).
    *   `vel_x`, `vel_y`: The initial velocity of the spawned projectiles.

### Particle Effect

*   `EntityLoad("data/entities/particles/poof_white.xml", pos_x, pos_y)`: Spawns a "poof_white" particle effect at the burst location.

### Entity Management

*   `EntityKill(entity_id)`: Destroys the original "pollen_ball_burst" projectile after its effects are complete.

## Example Usage (within the script)

```lua
local how_many = 16
local angle_inc = ( 2 * 3.14159 ) / how_many
local theta = 0

for i=1,how_many do
	local length = Random( 50, 250 ) -- Random velocity magnitude
	
	local vel_x = math.cos( theta ) * length
	local vel_y = math.sin( theta ) * length
	theta = theta + angle_inc

	-- Spawn a smaller pollen projectile
	shoot_projectile( entity_id, "data/entities/projectiles/pollen.xml", pos_x + vel_x * 0.05, pos_y + vel_x * 0.05, vel_x, vel_y )
end

-- Spawn a particle effect
EntityLoad( "data/entities/particles/poof_white.xml", pos_x, pos_y )

-- Destroy the original projectile
EntityKill( entity_id )
```