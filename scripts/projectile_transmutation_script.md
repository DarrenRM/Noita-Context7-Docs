---
title: Projectile Transmutation Script
category: scripts
---

# Projectile Transmutation Script

This script handles the transmutation of nearby projectiles into random animals and a visual effect. It's designed to be attached to an entity that will trigger this effect.

## Core Functionality

The script iterates through all entities tagged as "projectile". If a projectile is within a certain proximity to the entity running this script, it will be transmuted.

### Key Attributes & Elements

*   **Proximity Check:**
    *   `distance < 64`: The initial Manhattan distance check to see if a projectile is close enough.
    *   `distance < 48`: The Euclidean distance check for a more precise proximity.
*   **Projectile Component Modification:**
    *   `ProjectileComponent`: The script targets this component on projectiles.
    *   `on_death_explode = "0"`: Disables explosion on projectile death.
    *   `on_lifetime_out_explode = "0"`: Disables explosion when projectile lifetime ends.
*   **Randomization:**
    *   `SetRandomSeed( px + 325, py - 235 )`: Sets a random seed based on projectile position for consistent results within a localized area.
    *   `opts = { "duck", "sheep", "sheep_bat", "sheep_fly" }`: A table of possible animal entities to spawn.
    *   `Random( 1, #opts )`: Selects a random animal from the `opts` table.
*   **Entity Spawning:**
    *   `EntityLoad("data/entities/animals/" .. opt .. ".xml", px, py)`: Spawns the chosen random animal at the projectile's location.
    *   `EntityLoad("data/entities/particles/image_emitters/transmutation_effect.xml", px, py)`: Spawns a visual transmutation effect.
*   **Entity Destruction:**
    *   `EntityKill( projectile_id )`: Removes the original projectile after transmutation.

## Usage

This script is intended to be attached to an entity that will periodically check for and transmute nearby projectiles. The entity itself would likely have a `ScriptComponent` pointing to this Lua file.