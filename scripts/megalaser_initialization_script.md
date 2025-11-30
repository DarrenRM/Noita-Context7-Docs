---
title: Megalaser Initialization Script
category: scripts
---

---

# Megalaser Initialization Script

This script initializes the `megalaser` entity, specifically focusing on storing references to its associated beam entities.

## Key Functionality

*   **Entity Identification:** Retrieves the unique ID and position of the `megalaser` entity.
*   **Beam Reference Storage:** Locates up to 5 `megalaser_beam` entities within a radius of 5 units around the `megalaser`.
*   **Variable Storage:** For each found beam, it adds a `VariableStorageComponent` to the `megalaser` entity. This component stores the `beam_id` (the entity ID of the beam) as an integer, tagged with `beam_ref`. This is crucial for the `megalaser_launch.lua` script to interact with and control the beams.

## Core Components

### `EntityGetInRadiusWithTag`

This function is used to find entities with the tag `"megalaser_beam"` within a specified radius.

### `EntityAddComponent`

This function is used to add a `VariableStorageComponent` to the `megalaser` entity.

### `VariableStorageComponent`

This component is used to store key-value pairs associated with an entity. In this case, it stores the entity ID of each beam under the key `"beam_id"`.