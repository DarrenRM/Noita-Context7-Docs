---
title: Wand Ghost (Charmed) Entity
category: entities
---

# Wand Ghost (Charmed) Entity

This entity defines a charmed Wand Ghost, a creature that can be influenced by the player.

## Key Attributes

*   **`name`**: `$animal_wand_ghost` - The internal name for this entity.
*   **`tags`**: `mortal`, `hittable`, `homing_target`, `wand_ghost` - These tags define its fundamental properties and interactions.

## Base Entity Configuration

The Wand Ghost inherits its core functionality from `data/entities/base_wand_ghost.xml`.

### `Base` Component Overrides

*   **`CameraBoundComponent`**:
    *   `_enabled`: `0` - This component is disabled, meaning the ghost is not bound by camera proximity.
    *   `max_count`: `30` - Limits the maximum number of these entities that can exist simultaneously.
    *   `distance`: `160000` - The maximum distance from the camera at which this entity can exist.
*   **`GenomeDataComponent`**:
    *   `herd_id`: `player` - Indicates this entity belongs to the player's "herd" or faction.
    *   `food_chain_rank`: `7` - Defines its position in the game's food chain.
    *   `is_predator`: `1` - Marks this entity as a predator.
*   **`ItemPickUpperComponent`**:
    *   `is_immune_to_kicks`: `1` - The entity is immune to being kicked.
    *   `is_in_npc`: `1` - This entity is considered an NPC.

## Audio Configuration

*   **`AudioLoopComponent`**:
    *   `file`: `data/audio/Desktop/animals.bank` - Specifies the audio bank to use.
    *   `event_name`: `animals/ghost/movement_loop` - The sound event for its movement loop.
    *   `set_speed_parameter`: `1` - The movement speed will dynamically control an audio parameter.
    *   `auto_play`: `1` - The sound will start playing automatically.

## Lifetime and Scripting

*   **`LifetimeComponent`**:
    *   `lifetime`: `3600` - The entity will exist for 3600 frames (approximately 1 minute).
*   **`LuaComponent`**:
    *   `execute_every_n_frame`: `3599` - The script will execute just before the entity's lifetime ends.
    *   `remove_after_executed`: `1` - The entity will be removed after the script executes.
    *   `script_source_file`: `data/scripts/misc/drop_all_items.lua` - This script is executed to make the entity drop all its items.

## Notes

*   The commented-out `<Base file="data/entities/misc/effect_charm.xml"></Base>` indicates that charm effects are not directly applied via this method for this specific entity, likely due to compatibility issues with `PhysicsAnimalAI`.