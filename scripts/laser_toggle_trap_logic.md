---
title: Laser Toggle Trap Logic
category: scripts
---

---

# Laser Toggle Trap Logic

This script controls the behavior of a laser trap that can be toggled on and off. It interacts with a `VariableStorageComponent` to track its state and with `LaserEmitterComponent`s on its children to control laser emission.

## Core Functionality

The primary function of this script is to flip the state of a laser trap. When activated, it toggles between emitting and not emitting a laser.

### State Management

The trap's state is managed by a `VariableStorageComponent` named "status".

*   **`status` Variable:** This integer variable stores the current state:
    *   `0`: Off
    *   `1`: On

The script reads the current `status` value, inverts it (`1 - s`), and writes the new value back.

### Laser Emission Control

The script enables or disables laser emission based on the trap's current state.

*   **`EntitySetComponentsWithTagEnabled( entity_id, "laser_toggle", onoff )`:** This function enables or disables components tagged with "laser_toggle" based on the `onoff` boolean.
*   **Child Laser Emitters:** The script iterates through all children of the trap entity. If a child has a `LaserEmitterComponent`, its `is_emitting` property is set to the `onoff` state.

## Script Attributes

The script itself has a `LuaComponent` that dictates its execution frequency.

*   **`execute_every_n_frame`:** Set to `150`. This means the script's logic will run approximately every 150 frames, allowing for a relatively slow toggle update.

## Example Usage (Conceptual)

While the script itself doesn't define how it's triggered, it's designed to be part of a larger system. A common pattern would be:

1.  A trigger (e.g., a button, a pressure plate) activates this script.
2.  The script flips its internal `status`.
3.  The laser emitter on the trap entity (and potentially other associated components) is updated accordingly.

This script is a fundamental building block for creating dynamic laser-based puzzles and hazards in Noita.