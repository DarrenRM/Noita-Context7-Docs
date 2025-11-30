---
title: Boss Ghost Death Behavior
category: entities
---

# Boss Ghost Death Behavior

This script defines the behavior of the Boss Ghost entity upon death.

## Core Functionality

The `death` function is triggered when the Boss Ghost entity takes damage. It handles the entity's demise and any associated effects.

### Key Attributes & Actions

*   **`entity_id`**: Retrieves the unique identifier for the Boss Ghost entity.
*   **`x, y`**: Gets the current world coordinates of the Boss Ghost.
*   **`EntityLoad( "data/entities/items/pickup/heart_fullhp.xml", x, y )`**: Spawns a full HP heart pickup at the Boss Ghost's location.
*   **`EntityLoad( "data/entities/items/pickup/sun/sunseed.xml", x + 16, y )`**: Spawns a sunseed pickup slightly to the right of the Boss Ghost's location.
*   **`AddFlagPersistent( "miniboss_ghost" )`**: Adds a persistent flag to the game state, likely to mark that the miniboss ghost has been defeated. This can be used by other game systems to track progress or alter future events.