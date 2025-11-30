---
title: Wand Pickup Particle Effects
category: scripts
---

# Wand Pickup Particle Effects

This script handles the visual effects and logic associated with picking up a wand in Noita. It triggers particle effects and can activate special wand trap behaviors.

## Key Functions

### `item_pickup(entity_item, entity_who_picked, name)`

This is the primary function called when an item is picked up.

*   **`entity_item`**: The entity ID of the item being picked up.
*   **`entity_who_picked`**: The entity ID of the entity that picked up the item.
*   **`name`**: The internal name of the item.

## Core Logic

### Player Pickup Effects

When a player picks up an item, the script checks if it's a wand and if it has already been picked up by a player. If it's the first time a player picks it up, a visual effect is triggered.

*   **`GamePrintImportant("$itemtitle_wand_pickup", "")`**: Displays an important message to the player indicating a wand pickup.
*   **`shoot_projectile(...)`**: Spawns a particle emitter effect (`wand_effect.xml`) at the pickup location to visualize the wand being acquired.

### Wand Trap Interaction

The script also checks if the picked-up item has the tag "trap_wand". If so, it triggers a specific wand trap behavior.

*   **`string.find(entity_tags, "trap_wand")`**: Checks for the presence of the "trap_wand" tag within the entity's tags.
*   **`trigger_wand_pickup_trap(pos_x, pos_y)`**: Calls a function (presumably defined elsewhere, e.g., `wand_trap.lua`) to activate the wand trap at the item's position.

## Relevant Files

*   `data/scripts/lib/utilities.lua`: Contains utility functions used by this script.
*   `data/scripts/buildings/wand_trap.lua`: Contains the definition for `trigger_wand_pickup_trap`.
*   `data/entities/particles/image_emitters/wand_effect.xml`: The particle emitter definition for the wand pickup visual effect.