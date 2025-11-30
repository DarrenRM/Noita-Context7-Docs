---
title: Worm Death Script
category: scripts
---

# Worm Death Script

This script defines the behavior when a worm-type entity dies in Noita. It handles item drops and visual effects.

## Key Functions

### `death( damage_type_bit_field, damage_message, entity_thats_responsible, drop_items )`

This is the primary function called when the worm entity is killed.

*   **`damage_type_bit_field`**: A bitmask representing the type of damage that killed the entity.
*   **`damage_message`**: A string describing the damage.
*   **`entity_thats_responsible`**: The entity ID of the entity that caused the death.
*   **`drop_items`**: A boolean indicating whether items should be dropped.

## Core Logic

1.  **Self-Identification**: The script first gets the `entity_id` of the entity it's attached to and its `pos_x`, `pos_y` coordinates.
2.  **Random Seed**: A random seed is generated based on game frame number and entity position for deterministic randomness.
3.  **Heart Drop**: There's a 50% chance (`Random(1, 2) == 2`) to spawn a "heart" pickup item at the worm's death location.
4.  **Entity Kill (Commented Out)**: The line `EntityKill( entity_id )` is commented out. This implies that the entity's death is likely handled by the game engine or another script, and this script's primary role is managing the death *effects*.

## Dependencies

*   `dofile_once("data/scripts/lib/utilities.lua")`: Imports utility functions, likely including `Random` and `SetRandomSeed`.

## Example Usage (Conceptual)

This script would be attached to a worm entity's XML definition, likely within a `<script>` tag. When the game's damage system registers a fatal blow to that entity, this `death` function would be automatically invoked.

```lua
-- Example of how this script might be referenced in an entity XML
-- <entity name="worm_basic">
--     ...
--     <script name="data/scripts/animals/worm_death.lua" />
--     ...
-- </entity>
```