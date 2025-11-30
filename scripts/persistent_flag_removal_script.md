---
title: Persistent Flag Removal Script
category: scripts
---

# Persistent Flag Removal Script

This script provides a simple function to remove persistent flags in Noita. Persistent flags are used to track events or states that should persist across game sessions.

## Function: `test()`

This function demonstrates the usage of `RemoveFlagPersistent`.

### Purpose

*   Removes a specific persistent flag from the game.

### Usage

```lua
RemoveFlagPersistent( "flag_name" )
```

### Parameters

| Parameter   | Type   | Description                               |
| :---------- | :----- | :---------------------------------------- |
| `"flag_name"` | string | The name of the persistent flag to remove. |

### Example

```lua
function test()
	RemoveFlagPersistent( "test_flag" ) -- Removes the flag named "test_flag"
end
```