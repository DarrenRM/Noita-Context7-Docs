---
title: Rat Entity
category: entities
---

# Rat Entity

This document details the configuration of the "rat" entity in Noita, focusing on its AI, combat, physical attributes, and visual representation.

## Core Components

The rat entity is built upon a `Base` entity, inheriting common enemy functionalities.

### `Base` Entity Configuration

The `Base` entity incorporates several key components that define the rat's behavior and properties.

#### `ItemChestComponent`

*   **level**: `2` - Indicates the loot tier associated with this entity.

#### `AnimalAIComponent`

This component governs the rat's artificial intelligence and combat behavior.

*   **preferred\_job**: `JobDefault` - The default task the AI will attempt to perform.
*   **attack\_melee\_damage\_min**: `0.2` - The minimum damage dealt by melee attacks.
*   **attack\_melee\_damage\_max**: `0.4` - The maximum damage dealt by melee attacks.
*   **needs\_food**: `1` - The AI requires food to survive.
*   **attack\_ranged\_enabled**: `0` - Ranged attacks are disabled for this entity.
*   **can\_fly**: `0` - The rat cannot fly.
*   **attack\_melee\_max\_distance**: `10` - The maximum distance at which melee attacks can be initiated.
*   **attack\_melee\_action\_frame**: `3` - The frame within the attack animation when damage is applied.

#### `DamageModelComponent`

Defines the rat's health and how it reacts to damage.

*   **ragdoll\_filenames\_file**: `data/ragdolls/rat/filenames.txt` - Specifies the file containing ragdoll animation data.
*   **ragdoll\_offset\_y**: `-1` - Vertical offset for the ragdoll.
*   **hp**: `0.2` - The rat's hit points.
*   **air\_needed**: `1` - The entity requires air.

#### `SpriteComponent`

Controls the visual appearance of the rat.

*   **image\_file**: `data/enemies_gfx/rat.xml` - Path to the sprite definition file.
*   **offset\_x**: `10` - Horizontal offset for the sprite.
*   **offset\_y**: `12` - Vertical offset for the sprite.

#### `PathFindingComponent`

Manages the rat's movement and navigation capabilities.

*   **distance\_to\_reach\_node\_x**: `20` - Horizontal distance threshold for reaching a navigation node.
*   **distance\_to\_reach\_node\_y**: `20` - Vertical distance threshold for reaching a navigation node.
*   **frames\_to\_get\_stuck**: `20` - Number of frames before the AI considers itself stuck.
*   **can\_swim\_on\_surface**: `1` - The rat can swim on the surface of liquids.
*   **can\_dive**: `1` - The rat can dive into liquids.
*   **can\_jump**: `1` - The rat can jump.

#### `PathFindingGridMarkerComponent`

Used for pathfinding grid interactions.

*   **marker\_work\_flag**: `16` - A flag used for marking navigation grid cells.

#### `GenomeDataComponent`

Provides genetic information for AI and ecosystem simulation.

*   **herd\_id**: `rat` - Identifier for the rat's herd or species.
*   **food\_chain\_rank**: `10` - Its position in the food chain.
*   **is\_predator**: `1` - The rat is a predator.

#### `CharacterPlatformingComponent`

Defines movement parameters related to platforming.

*   **jump\_velocity\_y**: `-30` - The vertical velocity applied when jumping.
*   **run\_velocity**: `40` - The horizontal movement speed.

#### `HitboxComponent`

Defines the collision area for interactions.

*   **aabb\_min\_x**: `-5.5` - Minimum X-coordinate of the bounding box.
*   **aabb\_max\_x**: `5.5` - Maximum X-coordinate of the bounding box.
*   **aabb\_min\_y**: `-1.4` - Minimum Y-coordinate of the bounding box.
*   **aabb\_max\_y**: `3.5` - Maximum Y-coordinate of the bounding box.
*   **is\_enemy**: `1` - This hitbox belongs to an enemy.
*   **is\_item**: `0` - This hitbox is not an item.
*   **is\_player**: `0` - This hitbox does not belong to the player.

#### `CharacterDataComponent`

General character data, including collision and physics properties.

*   **collision\_aabb\_min\_x**: `-3.5` - Minimum X-coordinate for collision detection.
*   **collision\_aabb\_max\_x**: `3.5` - Maximum X-coordinate for collision detection.
*   **collision\_aabb\_min\_y**: `-3` - Minimum Y-coordinate for collision detection.
*   **collision\_aabb\_max\_y**: `3` - Maximum Y-coordinate for collision detection.
*   **buoyancy\_check\_offset\_y**: `-1` - Vertical offset for buoyancy checks.
*   **mass**: `0.4` - The mass of the rat.

### `AudioComponent`

Manages the sound effects associated with the rat.

*   **file**: `data/audio/Desktop/animals.bank` - The audio bank file.
*   **event\_root**: `animals/rat` - The root event name for rat sounds.

### `VariableStorageComponent`

Allows for custom variables to be stored with the entity.

*   **name**: `plague_rats` - A variable named "plague\_rats" is associated with this entity, potentially for special variants or behaviors.