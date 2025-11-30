---
title: Orb Boss Scream Entity
category: scripts
---

# Orb Boss Scream Entity

This script defines the behavior for an entity that acts as a "boss scream" orb in Noita. When this entity is spawned, it triggers a gameplay sound and a screen shake before being immediately destroyed.

## Key Attributes

*   **`entity_id`**: A unique identifier for the entity.
*   **`pos_x`, `pos_y`**: The X and Y coordinates of the entity's position in the game world.

## Core Functionality

1.  **Initialization**:
    *   The script first includes necessary helper functions from `game_helpers.lua` and `utilities.lua`.
    *   It retrieves the unique `entity_id` for the current entity.
    *   It gets the entity's world coordinates (`pos_x`, `pos_y`).

2.  **Gameplay Effects**:
    *   **`GamePlaySound`**: Plays a specific sound event: `"event_cues/orb_distant_monster/create"`. This sound is likely intended to alert the player to a boss's presence or a significant event.
    *   **`GameScreenshake`**: Triggers a screen shake with an intensity of `100`. This adds a visceral impact to the event.

3.  **Entity Destruction**:
    *   **`EntityKill(entity_id)`**: Immediately destroys the entity after its effects have been triggered. This suggests the orb is a one-time event trigger rather than a persistent object.

## Example Usage (Conceptual)

This script would typically be attached to an entity defined in a `.xml` file. For instance:

```xml
<entity name="orb_boss_scream">
    <components>
        <script name="data/scripts/items/orb_boss_scream.lua" />
        <!-- Other components like Transform, Sprite, etc. -->
    </components>
</entity>
```