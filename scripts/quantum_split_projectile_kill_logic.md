---
title: Quantum Split Projectile Kill Logic
category: scripts/
---

# Quantum Split Projectile Kill Logic

This script handles the termination logic for projectiles involved in the "quantum split" mechanic. It's responsible for spawning visual effects based on the projectile's quantum color and ensuring the split projectile is properly destroyed.

## Key Functionality

### Visual Effect Spawning

The script checks for specific tags on the projectile entity to determine which visual effect to spawn upon its destruction.

*   **`quantum_red`**: If the projectile has the `quantum_red` tag, it spawns `data/entities/misc/quantum_split_fx_red_die.xml`.
*   **`quantum_blue`**: If the projectile has the `quantum_blue` tag, it spawns `data/entities/misc/quantum_split_fx_blue_die.xml`.

### Split Projectile Termination

After handling visual effects, the script proceeds to terminate the "next" projectile in the quantum split chain.

*   It retrieves a stored variable (`next_quantum_entity`) which holds the ID of the projectile to be terminated.
*   It then modifies the `ProjectileComponent` of this "next" projectile to disable any explosion effects that might trigger on lifetime out or death.
*   Finally, it calls `EntityKill` on this "next" projectile to ensure it's properly removed from the game.

## Core Logic Breakdown

```lua
-- Load utility functions
dofile_once("data/scripts/lib/utilities.lua")

-- Get the root entity ID and its position
local entity_id    = EntityGetRootEntity( GetUpdatedEntityID() )
local pos_x, pos_y = EntityGetTransform( entity_id )

-- Retrieve the storage component holding the ID of the next quantum entity
local storage_comp = get_variable_storage_component(entity_id, "next_quantum_entity")

-- Spawn visual effects based on quantum color tags
if EntityHasTag(entity_id, "quantum_red") then
	EntityLoad("data/entities/misc/quantum_split_fx_red_die.xml", pos_x, pos_y)
elseif EntityHasTag(entity_id, "quantum_blue") then
	EntityLoad("data/entities/misc/quantum_split_fx_blue_die.xml", pos_x, pos_y)
end

-- Kill the current projectile entity
EntityKill(entity_id)

-- If no storage component is found, exit early
if not storage_comp then return end

-- Get the ID of the next projectile from the storage component
local next_id = ComponentGetValue2( storage_comp, "value_int" )

-- Get the ProjectileComponent of the next projectile
local projectile_comp = EntityGetFirstComponent(next_id, "ProjectileComponent")

-- Disable explosions for the next projectile
component_write( projectile_comp, {
	on_lifetime_out_explode = false,
	on_death_explode = false,
} )

-- Kill the next projectile
EntityKill(next_id)
```