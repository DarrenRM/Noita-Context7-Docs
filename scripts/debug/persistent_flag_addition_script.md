---
title: Persistent Flag Addition Script
category: scripts/debug
---

# Persistent Flag Addition Script

This script provides a simple function to add persistent flags in Noita. Persistent flags are game states that remain active across game sessions.

## Function: `test()`

This function demonstrates the usage of `AddFlagPersistent`.

### `AddFlagPersistent(flag_name)`

*   **Purpose:** Adds a persistent flag to the game.
*   **`flag_name` (string):** The unique identifier for the flag to be added.

#### Example Usage:

```lua
function test()
	AddFlagPersistent( "test_flag" )
end
```

This example will add a persistent flag named `"test_flag"` to the game. This flag will remain active even after the game is closed and reopened.