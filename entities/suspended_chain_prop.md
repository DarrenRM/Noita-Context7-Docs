---
title: Suspended Chain Prop
category: entities
---

# Suspended Chain Prop

This entity defines a suspended chain prop, commonly used for environmental elements in Noita. It utilizes physics components for realistic movement and a Lua script for dynamic generation.

## Key Components

### `PhysicsBody2Component`

Manages the physical properties of the chain.

*   `is_static`: `0` - The chain is not fixed and can move.
*   `allow_sleep`: `1` - The chain can enter a sleep state when not in motion to save performance.
*   `angular_damping`: `0.01` - Controls how quickly rotational movement slows down.
*   `linear_damping`: `0.3` - Controls how quickly linear movement slows down.
*   `fixed_rotation`: `0` - The chain is allowed to rotate freely.

### `PhysicsImageShapeComponent`

Defines the visual representation and physical shape of the chain.

*   `body_id`: `100` - Identifier for the physics body.
*   `is_root`: `1` - This component is the root of the physics shape.
*   `centered`: `1` - The image is centered on its origin.
*   `image_file`: `"data/props_gfx/suspended_chain.png"` - Specifies the texture file for the chain.
*   `material`: `"metal_prop"` - The material type, influencing interactions.

### `LuaComponent`

Handles the dynamic generation and behavior of the chain.

*   `script_source_file`: `"data/scripts/props/chain_to_ceiling.lua"` - The Lua script responsible for chain logic.
*   `execute_on_added`: `1` - The script runs immediately when the entity is added to the game.
*   `execute_every_n_frame`: `5` - The script's `on_frame` function is called every 5 frames.
*   `execute_times`: `-1` - The script will execute indefinitely.

### `VariableStorageComponent`

Stores variables used by the Lua script for chain generation.

*   `name`: `"chain_0_x"`
    *   `value_int`: `-1` - Stores an integer value for the X-coordinate offset.
*   `name`: `"chain_0_y"`
    *   `value_int`: `-5` - Stores an integer value for the Y-coordinate offset.