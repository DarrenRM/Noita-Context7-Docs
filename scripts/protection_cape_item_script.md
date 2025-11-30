---
title: Protection Cape Item Script
category: scripts
---

---

# Protection Cape Item Script

This script defines the behavior of the Protection Cape item when picked up by a player in Noita. It applies various protective effects and visually modifies the cape based on the type of protection.

## Core Functionality

The `item_pickup` function is the main entry point for this script. It's triggered when a player picks up the Protection Cape.

### Key Actions:

1.  **Determine Protection Type:** The script first identifies the specific protection granted by the cape. This is stored in a `VariableStorageComponent` and can be one of several types (e.g., `protection_radioactivity`, `protection_fire`, `breath_underwater`).
2.  **Load Game Effect:** Based on the determined protection type, a corresponding game effect entity (e.g., `effect_protection_radioactivity.xml`) is loaded and applied to the player.
3.  **Modify Cape Appearance:** The script iterates through the player's child entities to find the "cape" component. It then modifies the `cloth_color` and `cloth_color_edge` properties of the `VerletPhysicsComponent` to visually match the protection type.
4.  **Remove Item:** Finally, the picked-up item entity is destroyed.

## Protection Types and Visuals

The script defines a table `effect_metadatas` that maps protection types to their associated game effect entity files and visual properties for the cape.

### `effect_metadatas` Table:

| Key                    | `entity_file`                                      | `cloth_color` | `cloth_color_edge` | Description                               |
| :--------------------- | :------------------------------------------------- | :------------ | :----------------- | :---------------------------------------- |
| `protection_fire`      | `data/entities/misc/effect_protection_fire.xml`    | `0xFF7f6d54`  | `0xFF9c8970`       | Grants fire protection.                   |
| `protection_radioactivity` | `data/entities/misc/effect_protection_radioactivity.xml` | `0xFF546d7f`  | `0xFF70899c`       | Grants radioactivity protection.          |
| `breath_underwater`    | `data/entities/misc/effect_breath_underwater.xml`  | `0xFF546dff`  | `0xFF7089ff`       | Grants underwater breathing capability. |

*Note: Other protection types might exist or be added in future updates, but these are the ones explicitly defined in this script.*

## Dependencies

This script relies on the following utility files:

*   `data/scripts/game_helpers.lua`
*   `data/scripts/lib/utilities.lua`