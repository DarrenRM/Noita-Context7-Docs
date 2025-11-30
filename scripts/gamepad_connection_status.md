---
title: Gamepad Connection Status
category: scripts
---

# Gamepad Connection Status

This script provides a simple function to check if a gamepad is currently connected to the game.

## Functions

### `test()`

This function queries the game's internal state to determine if a gamepad is connected.

#### Usage

```lua
test()
```

#### Description

When called, `test()` will:
1. Call `GameGetIsGamepadConnected()` to retrieve a boolean value indicating gamepad status.
2. Print the string representation of this boolean value to the console.

#### Key Attributes

*   **`GameGetIsGamepadConnected()`**: This is the core Lua function used to query the gamepad connection status. It returns `true` if a gamepad is detected, and `false` otherwise.