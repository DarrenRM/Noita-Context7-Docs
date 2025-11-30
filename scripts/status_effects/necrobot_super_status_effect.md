---
title: Necrobot Super Status Effect
category: scripts/status_effects
---

# Necrobot Super Status Effect

This script defines a status effect that triggers a special revival for the "Necrobot Super" entity.

## Core Functionality

The `death()` function is the primary logic for this status effect. When the entity with this status effect dies, it attempts to load a specific revival entity.

### Key Attributes

*   **`death()` function:** This function is executed when the entity with this status effect is destroyed.
*   **`GetUpdatedEntityID()`:** Retrieves the ID of the entity that triggered the `death()` function.
*   **`EntityGetTransform( entity_id )`:** Gets the current position (x, y) of the entity.
*   **`EntityGetFilename( entity_id )`:** Retrieves the filename associated with the entity. This is used to ensure the effect only triggers for the intended entity.
*   **`EntityLoad( "data/entities/misc/necrobot_super_revive.xml", x, y )`:** This is the crucial part. If the entity's filename matches the expected one, this line loads a new entity (`necrobot_super_revive.xml`) at the original entity's position. This effectively revives or respawns the Necrobot Super in a special way.

## Usage Notes

*   This script is designed to be attached as a status effect to a specific entity (likely the "Necrobot Super").
*   The `necrobot_super_revive.xml` file must exist in the specified path for the revival to occur.
*   The condition `( file ~= nil ) and ( #file > 0 )` ensures that the revival logic only runs if the entity has a valid filename, preventing potential errors.