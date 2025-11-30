---
title: Orb Pickup - Loose Ground Test
category: scripts
---

# Orb Pickup - Loose Ground Test

This script defines the behavior when a specific orb item is picked up. It triggers visual effects and spawns loose ground chunks.

## Key Functionality

### `item_pickup` Function

This is the primary function executed when the orb is collected.

*   **Parameters:**
    *   `entity_item`: The entity representing the orb being picked up.
    *   `entity_who_picked`: The entity that picked up the orb (e.g., the player).
    *   `item_name`: The internal name of the orb item.

### Core Actions

1.  **Get Position:** Retrieves the `x` and `y` coordinates of the orb's current position.
2.  **Spawn Orb Effect:** Emits a particle effect associated with the orb using `shoot_projectile`.
    *   **Effect File:** `data/entities/particles/image_emitters/orb_effect.xml`
3.  **Spawn Loose Ground Chunks:** Loads and places multiple instances of `loose_chunks_lavalake.xml` around the orb's pickup location. This creates a visual effect of ground breaking apart.
    *   **Entity File:** `data/entities/misc/loose_chunks_lavalake.xml`
    *   **Spawn Offsets:** The chunks are spawned at various `x` and `y` offsets relative to the orb's position to create a scattered effect.
4.  **Kill Orb Entity:** Removes the orb item entity from the game world after it has been picked up and its effects have been triggered.

## Dependencies

*   `data/scripts/game_helpers.lua`
*   `data/scripts/lib/utilities.lua`

## Example Usage (Conceptual)

This script would be attached to an item entity definition in Noita, likely within an `item_pickup` component. When a player interacts with this item, the `item_pickup` function within this script will be invoked.