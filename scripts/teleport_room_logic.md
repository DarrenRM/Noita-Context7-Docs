---
title: Teleport Room Logic
category: scripts
---

# Teleport Room Logic

This script controls the behavior of a teleport room entity in Noita, specifically its interaction with a persistent flag related to a "miniboss_fish".

## Core Logic

The primary function of this script is to conditionally enable or disable a component tagged with `"enabled_by_liquid"` on the entity.

### Conditional Component Enabling

*   **Condition:** The script checks for the presence of a persistent flag named `"miniboss_fish"`.
*   **If `miniboss_fish` flag is present:** The component tagged `"enabled_by_liquid"` is enabled.
*   **If `miniboss_fish` flag is NOT present:** The component tagged `"enabled_by_liquid"` is disabled.

### Key Functions Used

*   `dofile_once("data/scripts/lib/utilities.lua")`: Includes utility functions, likely for common game scripting tasks.
*   `HasFlagPersistent( "miniboss_fish" )`: Checks if a persistent game flag is currently active.
*   `EntitySetComponentsWithTagEnabled( GetUpdatedEntityID(), "enabled_by_liquid", boolean_value )`: Modifies the enabled state of components on the current entity that possess the specified tag. `GetUpdatedEntityID()` retrieves the unique identifier of the entity being processed.