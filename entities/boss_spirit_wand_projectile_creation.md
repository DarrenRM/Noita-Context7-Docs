---
title: Boss Spirit Wand Projectile Creation
category: entities
---

# Boss Spirit Wand Projectile Creation

This script defines the behavior for a projectile fired by the Boss Spirit, specifically its ability to create and launch other projectiles.

## Core Functionality

The primary purpose of this script is to:
1.  Identify the type of projectile to be created.
2.  Detect nearby player units.
3.  If both conditions are met, it fires the identified projectile towards the nearest player.

## Key Components and Attributes

### Entity Identification and Transformation

*   `entity_id`: Retrieves the unique identifier for the current entity (the wand projectile).
*   `x`, `y`: Gets the current position of the wand projectile.
*   `radius`: Defines the detection radius (260 units) for nearby player units.

### Projectile Type Determination

*   `VariableStorageComponent`: This component is used to store and retrieve data associated with the entity.
*   `name == "type"`: Specifically looks for a variable named "type" within the `VariableStorageComponent`.
*   `value_string`: The value of the "type" variable, which is expected to be the name of the projectile to be created (e.g., "data/entities/projectiles/magic/fireball.xml").

### Target Detection

*   `EntityGetInRadiusWithTag(x, y, radius, "player_unit")`: This function searches for entities within the specified radius that have the tag "player_unit".

### Projectile Firing Logic

*   `string.len(proj) > 0`: Checks if a projectile type has been successfully identified.
*   `#targets > 0`: Checks if any player units were found within the detection radius.
*   `shoot_projectile_from_projectile(entity_id, proj, x, y, vel_x, vel_y)`: This is the core function that spawns a new projectile.
    *   `entity_id`: The entity from which the new projectile originates.
    *   `proj`: The path to the projectile's XML definition.
    *   `x`, `y`: The spawn position of the new projectile.
    *   `vel_x`, `vel_y`: The velocity components of the new projectile, calculated to aim towards the detected player.
*   `EntityAddTag(eid, "boss_alchemist")`: Assigns the tag "boss_alchemist" to the newly created projectile. This tag might be used by other systems to identify or interact with these specific projectiles.

## Example Usage (Conceptual)

Imagine the Boss Spirit fires a projectile with the following `VariableStorageComponent` entry:

```lua
VariableStorageComponent {
    __name = "VariableStorageComponent",
    variables = {
        { name = "type", value_string = "data/entities/projectiles/magic/lightning_bolt.xml" },
        -- other variables...
    }
}
```

When this projectile is active and a player is within 260 units, it will spawn a `lightning_bolt` projectile aimed at that player.