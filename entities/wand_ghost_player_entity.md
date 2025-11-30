---
title: Wand Ghost Player Entity
category: entities
---

# Wand Ghost Player Entity

This document describes the `wand_ghost_player.xml` entity, which defines the behavior and properties of a "wand ghost" specifically associated with the player in Noita.

## Key Attributes

The `wand_ghost_player.xml` entity inherits its base functionality from `base_wand_ghost.xml` and adds specific components to define its player-linked behavior.

### Entity Tags

*   `mortal`: Indicates the entity can be killed.
*   `hittable`: The entity can be targeted and hit by projectiles or other damage sources.
*   `homing_target`: The entity can be targeted by homing projectiles.
*   `wand_ghost`: Identifies this entity as a specific type of ghost related to wands.

### Base Entity

*   **File**: `data/entities/base_wand_ghost.xml`
    *   This indicates that the entity inherits core properties and behaviors from a common "wand ghost" base.

### Genome Data Component

This component defines the entity's role within the game's ecosystem.

*   `herd_id`: `"player"` - Crucially links this ghost to the player.
*   `food_chain_rank`: `7` - Assigns a rank in the food chain, suggesting its relative position in the game's AI hierarchy.
*   `is_predator`: `1` - Marks the entity as a predator.

### Lua Component

This component enables custom scripting for the entity.

*   `remove_after_executed`: `1` - The script will be removed after it has been executed once.
*   `script_source_file`: `data/scripts/animals/wand_ghost.lua` - Specifies the Lua script that controls the entity's dynamic behavior.

### Audio Loop Component

This component handles ambient sound effects for the entity.

*   `file`: `data/audio/Desktop/animals.bank` - The audio bank containing the sound events.
*   `event_name`: `animals/ghost/movement_loop` - The specific sound event for the ghost's movement.
*   `set_speed_parameter`: `1` - Allows the sound's speed to be dynamically adjusted based on the entity's movement.
*   `auto_play`: `1` - The sound will start playing automatically when the entity is spawned.