---
title: Angry Levitation Perk Logic
category: scripts
---

# Angry Levitation Perk Logic

This script defines the behavior for the "Angry Levitation" perk in Noita. When activated, it targets nearby enemies and applies a special effect.

## Core Functionality

The script identifies potential targets within a radius and applies the "angry_levitation" tag and associated components to them.

### Target Acquisition

*   **Radius:** Targets are searched within a radius of 240 units from the perk's entity.
*   **Tag:** Only entities with the "homing_target" tag are considered.

### Target Application Logic

The script iterates through potential targets and applies the "angry_levitation" effect under specific conditions:

1.  **Not Already Affected:** The target must not already have the "angry_levitation" tag.
2.  **Variable Storage Check:** It checks if a `VariableStorageComponent` named "angry_levitation" already exists on the target. This prevents re-application.
3.  **Not Polymorphed:** The target must not be polymorphed (i.e., `EntityHasTag("polymorphed")` is false).

### Components Added to Targets

If a target meets the criteria, the following components are added:

*   **`angry_levitation` Tag:** This tag is directly added to the entity.
*   **`VariableStorageComponent`:**
    *   `name`: "angry_levitation"
    *   `value_int`: Stores the `entity_id` of the perk that applied the effect.
*   **`LuaComponent`:**
    *   `script_death`: "data/scripts/perks/angry_levitation_death.lua" - This specifies a script to be executed when the target is destroyed or the effect ends.
    *   `execute_every_n_frame`: "-1" - Indicates that the `script_death` is not intended to be executed on a frame-by-frame basis but rather on an event (like death).

## Key Attributes

*   `GetUpdatedEntityID()`: Retrieves the ID of the entity executing this script (the perk itself).
*   `EntityGetTransform()`: Gets the position of the perk entity.
*   `EntityGetInRadiusWithTag()`: Finds entities within a specified radius and with a given tag.
*   `EntityHasTag()`: Checks if an entity possesses a specific tag.
*   `EntityGetComponent()`: Retrieves components attached to an entity.
*   `ComponentGetValue()`: Gets the value of a specific component property.
*   `EntityAddTag()`: Adds a tag to an entity.
*   `EntityAddComponent()`: Adds a new component to an entity.