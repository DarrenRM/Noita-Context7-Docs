---
title: Persistent Flag Checker
category: scripts
---

# Persistent Flag Checker

This script provides a simple function to check the status of a persistent flag in Noita. Persistent flags are game states that can be set and remembered across game sessions.

## Function: `test()`

This function demonstrates how to use `HasFlagPersistent` to check for a specific flag.

### Usage

```lua
function test()
	-- Checks if the persistent flag "test_flag" is set.
	local result = HasFlagPersistent( "test_flag" )

	if result then
		-- If the flag is set, print "flag: yes" to the game console.
		GamePrint( "flag: yes" )
	else
		-- If the flag is not set, print "flag: no" to the game console.
		GamePrint( "flag: no" )
	end
end
```

### Key Elements

*   **`HasFlagPersistent( flag_name )`**: This is the core Noita API function used to query the state of a persistent flag.
    *   `flag_name` (string): The unique identifier of the persistent flag to check.
*   **`GamePrint( message )`**: A utility function to display messages in the game's console. This is useful for debugging and providing feedback.
*   **Conditional Logic (`if/else`)**: Standard Lua control flow used to execute different actions based on whether the flag is found or not.