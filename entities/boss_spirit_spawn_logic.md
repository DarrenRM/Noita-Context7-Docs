---
title: Boss Spirit Spawn Logic
category: entities
---

# Boss Spirit Spawn Logic

This script handles the spawning of the "islandspirit" entity when triggered. It's a simple entity that loads another entity at its current position and then removes itself.

## Core Functionality

*   **Entity Loading:** Loads `data/entities/animals/boss_spirit/islandspirit.xml` at the current entity's coordinates.
*   **Self-Destruction:** Removes the entity that executed this script after the `islandspirit` is loaded.

## Key Attributes/Elements

*   `EntityLoad( "data/entities/animals/boss_spirit/islandspirit.xml", x, y )`: This is the primary function call that instantiates the `islandspirit` entity.
*   `EntityKill( entity_id )`: This function ensures that the spawning entity is removed from the game world after its task is complete.

## Usage Context

This script is typically attached to an entity that acts as a trigger for spawning the boss spirit. The exact trigger mechanism would be defined in the entity's XML definition.