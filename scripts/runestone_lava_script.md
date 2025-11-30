---
title: Runestone Lava Script
category: scripts
---

# Runestone Lava Script

This script is responsible for the behavior of the Lava Runestone in Noita.

## Core Functionality

The primary function of this script is to load the `runestone_lava.xml` entity at the runestone's current position when it is activated. This entity likely defines the visual appearance and any associated effects of the Lava Runestone.

## Key Elements

*   **`entity_id`**: Retrieves the unique identifier for the entity running this script.
*   **`x, y`**: Gets the current world coordinates of the entity.
*   **`EntityLoad("data/entities/misc/runestone_lava.xml", x, y)`**: This is the core function call. It loads the specified XML entity file at the determined `x` and `y` coordinates. This XML file will contain the actual definition of the Lava Runestone's visual and interactive properties.

## Dependencies

*   `dofile_once("data/scripts/lib/utilities.lua")`: This line ensures that the `utilities.lua` script is loaded and executed only once, providing access to various helper functions.

## Usage in Modding

When creating mods that interact with or modify runestones, understanding this script is crucial. You would typically:

1.  **Modify `runestone_lava.xml`**: To change the appearance, effects, or behavior of the Lava Runestone.
2.  **Reference this script**: If you are creating a new runestone type and want to replicate similar loading behavior.