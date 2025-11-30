---
title: Swing Puzzle Target Logic
category: scripts
---

# Swing Puzzle Target Logic

This script defines the behavior for a target entity in a swing puzzle. When activated, it triggers a reward, plays a sound, and then destroys itself.

## Key Functions

### `electricity_receiver_switched(on)`

This function is called when the electricity receiver associated with this target is switched.

*   **`on`**: A boolean indicating whether the receiver is switched on.

#### Behavior:

1.  **Get Entity ID**: Retrieves the ID of the current entity.
2.  **Get Transform**: Obtains the `x` and `y` coordinates of the entity.
3.  **Print Message**: Logs "done" to the console.
4.  **Spawn Reward**:
    *   Loads `data/entities/items/pickup/chest_random.xml` at a position offset from the target.
    *   Loads `data/entities/particles/image_emitters/magical_symbol.xml` at the same offset.
5.  **Play Sound**:
    *   Plays the sound `data/audio/Desktop/projectiles.snd` with the event `player_projectiles/crumbling_earth/create` at the offset position.
6.  **Kill Entity**: Destroys the target entity.