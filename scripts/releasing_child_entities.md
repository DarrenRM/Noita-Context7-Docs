---
title: Releasing Child Entities
category: scripts/
---

# Releasing Child Entities

This script defines a function `physics_body_modified` that, when triggered (typically by an entity being destroyed), iterates through all child entities of the modified entity. It then detaches each child from its parent and re-attaches it to a newly created, temporary "dummy" entity. This effectively releases the child entities, allowing them to exist and behave independently.

## Key Functionality

*   **`physics_body_modified( is_destroyed )`**: This is the primary function. It's designed to be called when an entity's physics body is modified, particularly when it's destroyed.
    *   **`is_destroyed`**: A boolean indicating if the entity was destroyed.

## Core Logic

1.  **Get Updated Entity ID**: Retrieves the ID of the entity whose physics body was modified.
2.  **Get Children**: Fetches a list of all entities that are children of the modified entity.
3.  **Iterate and Release**: For each child entity:
    *   **Get Transform**: Records the child's current position.
    *   **Create Dummy Entity**: Loads a `dummy_entity.xml` at the child's position. This acts as a temporary parent.
    *   **Remove from Parent**: Detaches the child from its original parent.
    *   **Add to New Parent**: Attaches the child to the newly created dummy entity.

## Example Usage (Conceptual)

This script would typically be attached to an entity that is designed to break apart into smaller, independent components upon destruction. For instance, a destructible object that, when shattered, releases several smaller projectiles or debris.

```lua
-- Example of how this script might be attached to an entity
-- (This is illustrative and not part of the provided script)

-- In an entity's XML file:
-- <entity name="breakable_object">
--     <components>
--         <component name="physics" />
--         <component name="script" filename="data/scripts/props/release_child_entities.lua" />
--     </components>
-- </entity>
```