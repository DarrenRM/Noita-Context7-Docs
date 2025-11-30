---
title: Random Card Pickup
category: entities
---

# Random Card Pickup

This entity represents a pickup item that grants the player a random card.

## Core Components

### LuaComponent

This component is responsible for the item's behavior.

*   **script\_source\_file**: `data/scripts/items/make_random_card.lua` - Specifies the Lua script that handles the logic for generating and granting a random card.
*   **execute\_on\_added**: `1` - The script will execute immediately when the item is added to the game world.
*   **remove\_after\_executed**: `1` - The item entity will be removed from the game world after the script has finished executing.

## Entity Tags

*   `drillable`: Indicates the entity can be destroyed by drilling.
*   `hittable`: Indicates the entity can be hit by projectiles or other attacks.