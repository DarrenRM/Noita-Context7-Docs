---
title: Worm Smaller Holes Perk
category: scripts
---

# Worm Smaller Holes Perk

This script modifies the behavior of "worm" and "lukki" entities when the "Worm Smaller Holes" perk is active. It ensures that these entities only stain the environment rather than eating through it.

## Core Functionality

The script iterates through entities tagged as "worm" and "lukki". For each entity, it checks if a `VariableStorageComponent` with the name "worm_smaller_holes" already exists. If not, it adds this component and a tag with the same name. Crucially, it then modifies the `CellEaterComponent` of the entity to set the `only_stain` property to `true`.

## Key Components and Attributes

### Entity Targeting

*   **`EntityGetWithTag("worm")`**: Retrieves all entities with the "worm" tag.
*   **`EntityGetWithTag("lukki")`**: Retrieves all entities with the "lukki" tag.

### Component Management

*   **`VariableStorageComponent`**:
    *   **`name`**: Set to `"worm_smaller_holes"` to identify entities affected by this perk.
    *   **`ComponentAddTag(cid, "worm_smaller_holes")`**: Adds a tag to the newly created `VariableStorageComponent` for easier identification.
*   **`CellEaterComponent`**:
    *   **`only_stain`**: This is the key attribute modified by the script. Setting it to `true` prevents the entity from consuming cells and only leaves a stain.

### Logic Flow

1.  **Get Entity ID and Transform**: The script starts by getting the current entity's ID and its transform (position).
2.  **Target Worms**: It searches for all entities tagged as "worm".
3.  **Process Worms**:
    *   For each worm, it checks for the presence of the "worm\_smaller\_holes" `VariableStorageComponent`.
    *   If the component is not found, it's added.
    *   The `CellEaterComponent` of the worm is then modified to set `only_stain` to `true`.
4.  **Target Lukkis**: It searches for all entities tagged as "lukki".
5.  **Process Lukkis**:
    *   The process for lukkis is identical to that for worms, ensuring they also only stain.

## Example Usage (Conceptual)

This script is designed to be triggered automatically when the "Worm Smaller Holes" perk is acquired by the player. It doesn't require direct invocation within gameplay.

```lua
-- This script is part of the perk system and is executed when the perk is active.
-- It modifies existing game entities.

-- Example of how the perk might be defined elsewhere (not part of this script):
-- Perk "Worm Smaller Holes":
--   - Grants the effect of this script.
--   - Applies to entities tagged "worm" and "lukki".
```