---
title: Runestone Activation Script
category: scripts
---

# Runestone Activation Script

This script handles the activation and deactivation logic for runestones in Noita. It interacts with `VariableStorageComponent` to track the active state of a runestone and controls components tagged with "activate".

## Core Functionality

The primary function `runestone_activate` manages the state changes.

### `runestone_activate( entity_id, forcestatus )`

*   **`entity_id`**: The unique identifier of the runestone entity.
*   **`forcestatus`** (optional):
    *   If provided, forces the runestone to the specified status (0 for inactive, 1 for active).
    *   If `nil`, the status is toggled (1 becomes 0, 0 becomes 1).

This function searches for a `VariableStorageComponent` on the entity. If found, it looks for a variable named "active".

*   **If "active" variable is found:**
    *   It reads the current integer value of "active".
    *   If `forcestatus` is not provided, it toggles the `status` (1 - current\_status).
    *   It updates the "active" variable's integer value to the new `status`.
    *   Based on the final `status`:
        *   If `status == 1` (active), it enables components tagged with "activate" on the entity.
        *   If `status == 0` (inactive), it disables components tagged with "activate" on the entity.

## Event Handlers

The script also defines functions to be called by game events.

### `kick()`

*   Called when the runestone is kicked.
*   Invokes `runestone_activate` with the entity's ID, toggling its active state.

### `throw_item()`

*   Called when the runestone is thrown.
*   Invokes `runestone_activate` with the entity's ID and forces the status to `1` (active).

### `item_pickup( entity_id )`

*   Called when the runestone is picked up.
*   Invokes `runestone_activate` with the provided `entity_id` and forces the status to `0` (inactive).