---
title: Statue Hand State Management
category: scripts
---

---

# Statue Hand State Management

This script manages the state transitions of statue hands based on game flags indicating how many have been destroyed. It handles the transformation of one statue hand entity into another and the eventual removal of all remaining statues.

## Key Functionality

The script checks for specific game flags (`statue_hands_destroyed_X`) and the presence of tags on the current entity (`statue_hand_X`) to determine the appropriate action.

### State Transitions

The core logic involves conditional transformations:

*   **3 Statues Destroyed:** If the `statue_hands_destroyed_3` flag is active, the current statue is removed, and a `teleportation_source.xml` particle effect is spawned at its location.
*   **2 Statues Destroyed:** If the entity has the `statue_hand_2` tag and the `statue_hands_destroyed_2` flag is active, the entity transforms into `statue_hand_3.xml`, a `teleportation_source.xml` particle effect is spawned, and the original entity is killed.
*   **1 Statue Destroyed:** If the entity has the `statue_hand_1` tag, the `statue_hands_destroyed_1` flag is active, and it does *not* have `statue_hand_3` or `statue_hand_2` tags, it transforms into `statue_hand_2.xml`, a `teleportation_source.xml` particle effect is spawned, and the original entity is killed.

### Important Notes

*   Damage, stains, and other visual effects do not carry over when a statue changes its state.
*   The script relies on `GameHasFlagRun()` to check for global game states.
*   `EntityLoad()` is used to spawn new entities, and `EntityKill()` is used to remove the current one.
*   `EntitySetTransform()` ensures the new entity inherits the position and rotation of the old one.