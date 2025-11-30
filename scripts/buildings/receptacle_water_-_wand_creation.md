---
title: Receptacle Water - Wand Creation
category: scripts/buildings
---

# Receptacle Water - Wand Creation

This script defines the behavior for a "receptacle" that, when successfully interacted with (presumably by a player or a specific game event), spawns a "wand_valtikka" and a magical symbol particle effect. It also plays a sound effect and then destroys the receptacle entity itself.

## Key Functions

### `material_area_checker_success( pos_x, pos_y )`

This is the primary function executed upon successful interaction with the receptacle.

*   **Parameters:**
    *   `pos_x`: The X-coordinate of the interaction point.
    *   `pos_y`: The Y-coordinate of the interaction point.

*   **Core Logic:**
    1.  Retrieves the `entity_id` of the receptacle that triggered the success.
    2.  Gets the current transform (position) of the receptacle.
    3.  **Spawns `wand_valtikka.xml`:** Loads a wand entity at a position slightly above the receptacle.
    4.  **Spawns `magical_symbol.xml`:** Loads a particle emitter for a magical symbol at the same position.
    5.  **Plays Sound:** Triggers a specific sound effect (`player_projectiles/crumbling_earth/create`) at the interaction location.
    6.  **Destroys Receptacle:** Removes the receptacle entity from the game.

## Key Entities and Assets

*   **`data/entities/items/wand_valtikka.xml`**: The entity that is spawned. This likely represents a specific type of wand in the game.
*   **`data/entities/particles/image_emitters/magical_symbol.xml`**: A particle effect that is spawned, visually indicating a magical event.
*   **`data/audio/Desktop/projectiles.snd`**: The sound file associated with the event, specifically the "player\_projectiles/crumbling\_earth/create" event within it.

## AI Modding Considerations

This script is a straightforward example of event-driven entity spawning. For AI-assisted modding:

*   **Trigger Conditions:** Understanding what triggers `material_area_checker_success` is crucial. This might involve player interaction, specific spell effects, or other game mechanics.
*   **Entity Placement:** The fixed offset (`y-85`) for spawning the wand and symbol can be adjusted to change their relative positions.
*   **Asset Swapping:** The `EntityLoad` calls can be modified to spawn different wands, particle effects, or even other types of entities upon successful interaction.
*   **Sound Customization:** The `GamePlaySound` call can be altered to play different sound effects.
*   **Conditional Spawning:** More complex logic could be added to `material_area_checker_success` to conditionally spawn different items based on player inventory, game state, or other factors.