---
title: Receptacle Oil - AI Modding Documentation
category: scripts
---

---

# Receptacle Oil - AI Modding Documentation

This documentation outlines the functionality of the `receptacle_oil.lua` script, designed for AI-assisted modding in Noita. This script defines the behavior of an oil receptacle that triggers specific events upon successful material detection.

## Core Functionality

The primary purpose of this script is to act as a trigger. When a specific material is detected within its area, it spawns a wand, a magical symbol particle effect, plays a sound, and then destroys itself.

### Key Attributes and Elements

*   **`material_area_checker_success( pos_x, pos_y )`**: This is the main function executed when the material detection condition is met.
    *   **`GetUpdatedEntityID()`**: Retrieves the unique identifier of the entity that triggered this function.
    *   **`EntityGetTransform(entity_id)`**: Gets the current position (`x`, `y`) of the triggering entity.
    *   **Position Adjustment**: The script slightly offsets the spawn position:
        *   `x = x + 72`
        *   `y = y - 22`
    *   **`EntityLoad("data/entities/items/wand_ruusu.xml", x, y)`**: Spawns the `wand_ruusu.xml` entity at the calculated position. This is a key outcome of the trigger.
    *   **`EntityLoad("data/entities/particles/image_emitters/magical_symbol.xml", x, y)`**: Spawns a visual particle effect (`magical_symbol.xml`) at the same position.
    *   **`GamePlaySound("data/audio/Desktop/projectiles.snd", "player_projectiles/crumbling_earth/create", x, y)`**: Plays a specific sound effect associated with the creation of the spawned entities.
    *   **`EntityKill(entity_id)`**: Removes the oil receptacle entity itself after its task is complete.

## Usage for AI Modding

When integrating this script into a mod, consider the following:

*   **Trigger Condition**: The script relies on an external mechanism (likely a `MaterialAreaChecker` component) to detect a specific material. The exact material is not defined within this script itself but would be configured on the entity using this script.
*   **Spawned Entities**: The script consistently spawns `wand_ruusu.xml` and `magical_symbol.xml`. If you wish to spawn different entities, you will need to modify the `EntityLoad` calls.
*   **Sound Effect**: The `GamePlaySound` call is hardcoded. To change the sound, update the path and event name.
*   **Self-Destruction**: The `EntityKill` call ensures the receptacle is a one-time trigger. Remove this line if you want the receptacle to persist.

This script provides a foundational example of an entity that reacts to its environment by spawning other entities and effects. It's a good starting point for creating custom trigger-based mechanics in Noita mods.