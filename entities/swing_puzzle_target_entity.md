---
title: Swing Puzzle Target Entity
category: entities
---

# Swing Puzzle Target Entity

This entity represents a target for a swing puzzle, typically activated by electricity.

## Key Components

### `ElectricityReceiverComponent`

This component enables the entity to receive and react to electrical signals.

*   **`radius`**: The radius within which electrical signals are detected.
    *   `6`: The detection radius for this target.

### `LuaComponent`

This component links the entity to a Lua script for custom behavior.

*   **`script_electricity_receiver_switched`**: Specifies the Lua script to execute when the entity receives an electrical signal.
    *   `data/scripts/buildings/swing_puzzle_target.lua`: The script responsible for handling the swing puzzle logic when this target is activated.