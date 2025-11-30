---
title: Ethereal Check Script
category: scripts
---

# Ethereal Check Script

This script determines if an entity should have the "magic_eye" component enabled based on the presence of nearby "evil_eye" entities with a specific "magic_eye_check" light component.

## Core Logic

The script performs the following checks:

1.  **Find Nearby Evil Eyes:** It searches for entities with the tag "evil_eye" within a `radius` of 200 units around the current entity.
2.  **Check for Magic Eye Component:** For each found "evil_eye", it checks if it has a `LightComponent` with the tag "magic_eye_check".
3.  **Determine Ethereal Status:**
    *   If at least one "evil_eye" with the "magic_eye_check" component is found (`found` becomes `true`), the entity is considered "ethereal".
    *   If no such "evil_eye" is found (`found` remains `false`), the entity is not "ethereal".
4.  **Apply/Remove Magic Eye Component:**
    *   If the entity is determined to be "ethereal" and *does not* currently have the "magic_eye" component enabled, it enables the "magic_eye" component and spawns a "poof_blue" particle effect.
    *   If the entity is *not* "ethereal" and *does* currently have the "magic_eye" component enabled, it disables the "magic_eye" component and spawns a "poof_blue" particle effect.

## Key Variables and Functions

*   `entity_id`: The ID of the entity running this script.
*   `x`, `y`: The world coordinates of the entity.
*   `radius`: The search radius for nearby "evil_eye" entities (set to 200).
*   `eyes`: A table containing entities found within the specified radius with the tag "evil_eye".
*   `found`: A boolean flag indicating whether an "evil_eye" with the "magic_eye_check" component was found.
*   `EntityGetInRadiusWithTag(x, y, radius, tag)`: Retrieves entities within a given radius and with a specific tag.
*   `EntityGetFirstComponent(entity_id, component_name, tag)`: Retrieves the first component of a specified type and tag from an entity.
*   `EntitySetComponentsWithTagEnabled(entity_id, tag, enabled)`: Enables or disables components with a specific tag on an entity.
*   `EntityLoad(filepath, x, y)`: Loads an entity from an XML file at specified coordinates.

## Relevant Tags

*   `evil_eye`: Tag applied to entities that act as "evil eyes".
*   `magic_eye_check`: Tag used within the `LightComponent` of "evil_eye" entities to signify their "magic eye" status.
*   `magic_eye`: Tag applied to the `DamageModelComponent` (or other relevant components) that controls the ethereal behavior.

## Example Usage (Conceptual)

This script is typically attached to an entity that needs to dynamically change its behavior or appearance based on the presence of "evil eyes". For instance, an enemy that becomes ethereal (and potentially invulnerable or harder to hit) when near a specific type of magical ward.

```lua
-- Example of an entity that might use this script
-- (This is conceptual and not part of the provided script)

-- In the entity's XML:
-- <entity name="my_ethereal_creature">
--   <script name="data/scripts/animals/ethereal_check.lua" />
--   <components>
--     <DamageModelComponent enabled="1" hp="10" />
--     <TagComponent tag="magic_eye" /> -- This tag is toggled by the script
--     ... other components ...
--   </components>
-- </entity>

-- In an "evil_eye" entity's XML:
-- <entity name="magic_ward">
--   <components>
--     <LightComponent radius="50" intensity="1" red="0" green="0" blue="1" name="magic_eye_check" />
--     <TagComponent tag="evil_eye" />
--     ... other components ...
--   </components>
-- </entity>
```