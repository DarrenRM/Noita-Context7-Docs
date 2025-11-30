---
title: Boss Ghost Damage Handling
category: entities
---

---

# Boss Ghost Damage Handling

This script defines how the Boss Ghost entity reacts to receiving damage.

## `damage_received` Function

This function is called when the Boss Ghost entity takes damage.

### Key Actions:

*   **Iterates through children:** It checks all child entities of the Boss Ghost.
*   **Identifies Lasers:** It specifically looks for child entities tagged with `"boss_ghost_lasers"`.
*   **Updates Laser Status:** For each identified laser child, it increments a `value_float` stored in a `VariableStorageComponent` named `"laser_status"`. This likely controls the intensity or progression of the boss's laser attacks.

### Relevant Components:

*   **`VariableStorageComponent`**: Used to store and modify the `laser_status` float value.