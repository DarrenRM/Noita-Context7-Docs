---
title: Knockback Particle
category: particles
---

# Knockback Particle

This script is responsible for spawning a "knockback star" particle effect at the entity's current position.

## Core Functionality

The script performs the following actions:

1.  **Includes Utilities:** Loads necessary utility functions from `data/scripts/lib/utilities.lua`.
2.  **Gets Entity Information:** Retrieves the unique ID and current world position (`pos_x`, `pos_y`) of the entity executing this script.
3.  **Spawns Particle:** Loads and places the `knockback_star.xml` particle entity at the determined position.

## Key Elements

*   **`dofile_once("data/scripts/lib/utilities.lua")`**: Ensures utility functions are available.
*   **`GetUpdatedEntityID()`**: Retrieves the ID of the entity running the script.
*   **`EntityGetTransform(entity_id)`**: Gets the world coordinates of the entity.
*   **`EntityLoad("data/entities/particles/knockback_star.xml", pos_x, pos_y)`**: This is the primary function that instantiates the visual knockback particle effect.

## Associated Files

*   **`data/entities/particles/knockback_star.xml`**: This XML file defines the visual properties and behavior of the knockback particle itself.