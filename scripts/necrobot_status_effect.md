---
title: Necrobot Status Effect
category: scripts
---

---

# Necrobot Status Effect

This script defines the behavior for the "necrobot" status effect in Noita. When an entity with this status effect dies, it triggers a revival mechanism.

## Core Functionality

The primary function of this script is to handle the death of an entity that has the `necrobot` status effect applied.

### `death()` Function

This function is called when an entity with the `necrobot` status effect is destroyed.

*   **Entity Identification:** It first retrieves the `entity_id` of the dying entity.
*   **Position Retrieval:** It then gets the `x` and `y` coordinates of the dying entity.
*   **File Retrieval:** It attempts to get the filename (`file`) associated with the dying entity. This is crucial for the revival process.
*   **Revival Entity Loading:**
    *   If a valid filename is found, it loads a specific revival entity: `data/entities/misc/necrobot_revive.xml` at the dying entity's position.
    *   It then searches for a `VariableStorageComponent` within the newly loaded revival entity, specifically looking for a variable named `necrobot_entity_file`.
    *   If this component is found, its `value_string` is updated to store the filename of the original dying entity. This allows the revival entity to know what to reconstruct.

## Key Components Involved

*   **`death()` function:** The main logic for handling the status effect's death event.
*   **`EntityGetUpdatedEntityID()`:** Retrieves the ID of the entity that triggered the event.
*   **`EntityGetTransform()`:** Gets the position of an entity.
*   **`EntityGetFilename()`:** Retrieves the filename of an entity.
*   **`EntityLoad()`:** Loads an entity from an XML file at a specified position.
*   **`EntityGetFirstComponent()`:** Finds the first component of a specific type on an entity.
*   **`VariableStorageComponent`:** A component used to store arbitrary values, in this case, the filename for revival.
*   **`ComponentSetValue2()`:** Sets the value of a component.

## Associated Files

*   `data/entities/misc/necrobot_revive.xml`: The entity responsible for the revival process.