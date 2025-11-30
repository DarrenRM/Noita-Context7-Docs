---
title: Roboguard Shot Example
category: scripts
---

# Roboguard Shot Example

This example demonstrates a basic Lua script for a projectile, intended to be attached to an entity using the `<LuaComponent script_shot="...">` tag.

## Key Functionality

The primary function of this script is to execute custom logic when a projectile is fired.

### `shot( projectile_id )`

This function is called when the projectile associated with this script is fired.

*   **`projectile_id`**: A string identifier for the projectile.

**Example Usage:**

```lua
-- Add <LuaComponent script_shot="data/scripts/_examples/roboguard_shot.lua" > to the entity

function shot( projectile_id )
	print("shot")
	-- put custom code here
end
```

**Note:** This is a minimal example. In a real mod, you would implement more complex behaviors within the `shot` function, such as:

*   Modifying projectile properties (speed, damage, spread).
*   Spawning additional entities or particles.
*   Applying status effects.
*   Playing custom sounds.