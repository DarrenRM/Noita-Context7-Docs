---
title: Unlock Item Action
category: scripts
---

# Unlock Item Action

This script demonstrates a simple action to unlock an item in Noita.

## Function: `unlock()`

This function is the core of the script. It calls the `UnlockItem` function to make a specific item available to the player.

### Key Elements:

*   **`UnlockItem(itemName)`**: This is the primary function used to unlock an item.
    *   `itemName`: A string representing the internal ID of the item to be unlocked.

## Example Usage:

```lua
function unlock()
	UnlockItem( "LIGHT_BULLET" )
end

unlock()
```

In this example, calling `unlock()` will unlock the item with the internal ID `"LIGHT_BULLET"`.