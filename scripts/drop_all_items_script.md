---
title: Drop All Items Script
category: scripts
---

# Drop All Items Script

This script is a simple utility designed to make an entity drop all items it is currently holding.

## Functionality

The core of this script relies on the `GameDropAllItems` function, which is a built-in Noita game function.

### Key Function

*   `GameDropAllItems( entity_id )`: This function takes an entity ID as input and causes that entity to drop all items it possesses.

## Usage

This script is intended to be attached to an entity within the Noita game world. When the entity's script is executed, it will trigger the dropping of its inventory.

### Example Implementation

```lua
local entity_id = GetUpdatedEntityID()
GameDropAllItems( entity_id )
```

This code snippet first retrieves the unique identifier for the entity that the script is attached to, and then passes that ID to the `GameDropAllItems` function.