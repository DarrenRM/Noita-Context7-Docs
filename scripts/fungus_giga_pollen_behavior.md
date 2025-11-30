---
title: Fungus Giga Pollen Behavior
category: scripts
---

# Fungus Giga Pollen Behavior

This script defines the behavior for a "Fungus Giga Pollen" entity in Noita, specifically its projectile-firing mechanism.

## Core Functionality

The primary function of this script is to detect nearby player units and, if found, trigger the firing of a "pollen" projectile.

### Key Attributes and Elements

*   **`entity_id`**: Retrieves the unique identifier for the current entity.
*   **`x`, `y`**: Gets the current world coordinates of the entity.
*   **`targets`**: An array storing entities within a specified radius that possess the "player\_unit" tag.
*   **`EntityGetInRadiusWithTag( x, y, 64, "player_unit" )`**: This function searches for entities tagged as "player\_unit" within a 64-unit radius around the entity's position.
*   **`if ( #targets > 0 ) then ... end`**: This conditional block executes the enclosed code only if at least one player unit is detected within the radius.
*   **`SetRandomSeed( x + entity_id, y + GameGetFrameNum() )`**: Initializes the random number generator using the entity's position and the current game frame number to ensure varied behavior.
*   **`shoot_projectile( entity_id, "data/entities/projectiles/pollen.xml", x, y, Random( -300, 300 ), Random( -300, 10 ) )`**: This function is called to fire a projectile.
    *   **`entity_id`**: The entity that is firing the projectile.
    *   **`"data/entities/projectiles/pollen.xml"`**: The XML definition of the projectile to be fired.
    *   **`x`, `y`**: The origin point of the projectile.
    *   **`Random( -300, 300 )`**: A random horizontal velocity for the projectile, ranging from -300 to 300.
    *   **`Random( -300, 10 )`**: A random vertical velocity for the projectile, ranging from -300 to 10.

## Usage Notes for Modding

*   This script is designed to be attached to an entity that should periodically shoot pollen projectiles when the player is near.
*   The detection radius (`64`) and projectile properties (velocity) can be adjusted to fine-tune the behavior.
*   The projectile itself is defined in `data/entities/projectiles/pollen.xml`, which would need to be created or modified separately.