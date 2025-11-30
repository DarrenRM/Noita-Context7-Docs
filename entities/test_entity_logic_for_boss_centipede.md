---
title: Test Entity Logic for Boss Centipede
category: entities
---

# Test Entity Logic for Boss Centipede

This document describes a test entity script designed to interact with other entities based on specific tags and modify its own appearance and behavior. It's likely a debugging or experimental tool.

## Core Functionality

The script's primary function is to:

1.  **Detect Target Entities:** It searches for entities within a radius that possess the "noita" tag.
2.  **Process Targets:** If "noita" entities are found, it kills them.
3.  **Self-Modification:** Upon successful target processing, it applies a new tag ("best\_gymtipz") to itself, makes this tag persistent, and changes its sprite to `data/enemies_gfx/body_old_test.xml`.
4.  **Child Entity Modification:** It iterates through all child entities, finds their `SpriteComponent`, and if the `image_file` does not end with `_green.xml`, it appends `_green.xml` to the filename.
5.  **Component Disabling:** It disables components tagged with "testcheck" on the entity itself.

## Key Attributes and Elements

### Entity Identification and Transformation

*   `entity_id`: Retrieves the unique identifier for the current entity.
*   `x`, `y`: Stores the current world coordinates of the entity.

### Target Detection

*   `test = get_flag_name( "noita" )`: Defines the tag to search for.
*   `targets = EntityGetInRadiusWithTag( x, y, 48, test )`: Finds all entities within a 48-unit radius that have the "noita" tag.

### Conditional Execution

*   `if ( #targets > 0 ) then ... end`: The main block of code executes only if at least one "noita" entity is found.

### Entity Manipulation

*   `EntityKill( v )`: Destroys a target entity.
*   `EntityAddTag( entity_id, result )`: Adds the "best\_gymtipz" tag to the current entity.
*   `AddFlagPersistent( result )`: Ensures the "best\_gymtipz" tag remains even after game reloads.

### Sprite Component Modification

*   `s = EntityGetFirstComponent( entity_id, "SpriteComponent" )`: Gets the primary `SpriteComponent` of the entity.
*   `ComponentSetValue2( s, "image_file", "data/enemies_gfx/body_old_test.xml" )`: Changes the sprite's image file.

### Child Entity Sprite Modification

*   `c = EntityGetAllChildren( entity_id )`: Retrieves all child entities.
*   `sprite = EntityGetComponent( v, "SpriteComponent" )`: Gets the `SpriteComponent` of a child entity.
*   `string.sub( f, -10 ) ~= "_green.xml"`: Checks if the sprite's image file already ends with `_green.xml`.
*   `f = string.sub( f, 1, #f - 4 ) .. "_green.xml"`: Modifies the image file path to append `_green.xml`.

### Component Disabling

*   `EntitySetComponentsWithTagEnabled( entity_id, "testcheck", false )`: Disables all components on the entity that have the "testcheck" tag.

## Example Usage (Conceptual)

This script would be attached to an entity. When that entity is spawned and encounters other entities tagged "noita" within its vicinity, it would eliminate them and then visually transform itself, also altering the appearance of its children. This suggests a role in a boss encounter or a dynamic environmental event.