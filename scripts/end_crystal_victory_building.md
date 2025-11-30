---
title: End Crystal Victory Building
category: scripts
---

# End Crystal Victory Building

This script defines the behavior of the "End Crystal" building, which is triggered upon victory in Noita. It handles loading the victory scene, spawning a teleport entity, and distributing random spell cards to the player.

## Key Functionality

### Victory Scene Loading
- Loads a placeholder pixel scene (`ending_placeholder_victory.png`) and its visual counterpart (`ending_placeholder_victory_visual.png`) at the crystal's location.
- Spawns a `teleport_ending_victory.xml` entity, which likely handles the transition to the victory screen or credits.

### Spell Card Distribution
- **Card Selection Logic:** The script iterates through a list of available spell `actions` (presumably defined elsewhere). It checks if a spell's `spawn_level` property includes `biomeid = 6` (which corresponds to the victory biome).
- **Random Card Spawning:** If valid cards are found for the victory biome, the script selects 5 random cards from the `validcards` table.
- **Item Entity Creation:** For each selected card, it creates an item entity using `CreateItemActionEntity` at a specific position relative to the crystal.
- **Duplicate Prevention:** Once a card is chosen and spawned, it's removed from the `validcards` table to prevent duplicates within the 5 spawned cards.

## Key Attributes/Elements

| Attribute/Element | Description |
|---|---|
| `entity_id` | The unique identifier for the End Crystal entity. |
| `x`, `y` | The world coordinates of the End Crystal. |
| `LoadPixelScene()` | Function to load the visual elements of the victory scene. |
| `EntityLoad()` | Function to load the teleport entity for victory progression. |
| `actions` | A global table (assumed) containing all available spell actions and their properties. |
| `thisitem.spawn_level` | A string property of a spell action, indicating the biomes it can spawn in. |
| `biomeid = 6` | The specific biome ID representing the victory condition. |
| `validcards` | A table to store the IDs of spell cards that can spawn in the victory biome. |
| `SetRandomSeed()` | Initializes the random number generator for consistent card selection within a game session. |
| `Random()` | Generates a random number within a specified range. |
| `CreateItemActionEntity()` | Spawns a collectible item entity in the game world. |