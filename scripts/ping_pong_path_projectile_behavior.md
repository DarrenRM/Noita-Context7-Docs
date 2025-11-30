---
title: Ping Pong Path Projectile Behavior
category: scripts/
---

# Ping Pong Path Projectile Behavior

This script defines the behavior for projectiles that exhibit a "ping pong" effect, meaning they bounce off surfaces and change direction. It dynamically adjusts the projectile's behavior based on its current velocity.

## Key Attributes and Logic

This script primarily modifies the `VelocityComponent` and `LuaComponent` of the projectile entity.

### Velocity-Based Execution Rate

The script calculates an `execute_every_n_frame` value for the projectile's `LuaComponent` based on its current velocity. This means faster projectiles will have their behavior updated more frequently, leading to more rapid bouncing.

*   **`exec_wait_min`**: Minimum frames to wait between execution (default: 4).
*   **`exec_wait_max`**: Maximum frames to wait between execution (default: 50).
*   **`min_vel`**: The velocity threshold below which the projectile's behavior is disabled (default: 60).
*   **Velocity Mapping**: The `exec_wait` value is mapped from the projectile's velocity range (`min_vel` to 600) to the execution frame range (`exec_wait_max` to `exec_wait_min`). This ensures that as velocity increases, the execution delay decreases.
*   **Clamping**: The calculated `exec_wait` is clamped between `exec_wait_min` and `exec_wait_max` to ensure it stays within defined bounds.

### Bounce Mechanics

When the projectile's velocity is above the `min_vel` threshold, the script applies a bounce effect by reversing and dampening its velocity.

*   **`dampening`**: A factor applied to the reversed velocity, reducing its magnitude with each bounce (default: 0.85).
*   **Velocity Reversal**: Both `vel_x` and `vel_y` are multiplied by `-1` to reverse their direction.
*   **Jump Component**: A small upward velocity component (`jump`) is added to `vel_y` to simulate a slight lift after each bounce. This is calculated as 10% of the current velocity magnitude.

### Entity Management

*   **`GetUpdatedEntityID()`**: Retrieves the unique identifier for the projectile entity.
*   **`EntityGetTransform()`**: Gets the current position and radius of the entity.
*   **`EntityGetFirstComponent()`**: Retrieves the `VelocityComponent` and `LuaComponent` associated with the projectile.
*   **`ComponentGetValueVector2()`**: Reads the `mVelocity` vector from the `VelocityComponent`.
*   **`ComponentSetValueVector2()`**: Updates the `mVelocity` vector in the `VelocityComponent`.
*   **`EntityGetComponent()`**: Retrieves all `LuaComponent` instances with the tag "pingpong_path".
*   **`EntitySetComponentIsEnabled()`**: Disables the `LuaComponent` when the projectile's velocity drops below `min_vel`.
*   **`ComponentSetValue()`**: Updates the `execute_every_n_frame` property of the `LuaComponent`.

## Lua Code Snippet

```lua
dofile_once( "data/scripts/lib/utilities.lua" )

local exec_wait_min = 4
local exec_wait_max = 50
local min_vel = 60
local dampening = 0.85

local entity_id = GetUpdatedEntityID()
local pos_x, pos_y, rad = EntityGetTransform( entity_id )

local velocity_comp = EntityGetFirstComponent( entity_id, "VelocityComponent")
if velocity_comp == nil then return end

local vel_x,vel_y = ComponentGetValueVector2( velocity_comp, "mVelocity")
local vel = get_magnitude(vel_x, vel_y)
local lua_comps = EntityGetComponent(entity_id, "LuaComponent", "pingpong_path")
if lua_comps == nil then return end

-- disable once velocity is too low
if vel < min_vel then
	for i=1,#lua_comps do
		EntitySetComponentIsEnabled( entity_id, lua_comps[i], false)
	end
	return
end

-- set execute pace based on velocity: faster projectiles bounce more frequently
local exec_wait = map(vel, min_vel, 600, exec_wait_max, exec_wait_min)
exec_wait = clamp(exec_wait, exec_wait_min, exec_wait_max)
exec_wait = math.floor(exec_wait)
for i=1,#lua_comps do
	ComponentSetValue( lua_comps[i], "execute_every_n_frame", exec_wait)
end
--print("vel: " .. vel .. ", delay: " .. exec_wait)

-- bounce
vel_x = -vel_x * dampening
local jump = vel * 0.1
vel_y = -vel_y * dampening - jump
ComponentSetValueVector2( velocity_comp, "mVelocity", vel_x, vel_y)
```