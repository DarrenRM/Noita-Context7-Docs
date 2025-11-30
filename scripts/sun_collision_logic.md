---
title: Sun Collision Logic
category: scripts
---

# Sun Collision Logic

This script defines the behavior when a "sun" entity collides with specific targets, triggering a powerful "supernova" event.

## Core Functionality

When the sun entity encounters any entities tagged with `"seed_f"`, it initiates a chain reaction:

*   **Target Elimination:** All entities tagged with `"seed_f"` are immediately destroyed.
*   **Supernova Visuals & Audio:** A visual supernova effect is spawned at the sun's location, accompanied by a screen shake and a distinct sound effect.
*   **Player & Mortal Effects:**
    *   Players are afflicted with an "eradicate" effect, spawning a child entity that also triggers a supernova particle effect at their location.
    *   Other "mortal" entities (those with a `DamageModelComponent`) receive a significant amount of curse damage (500), causing them to be "DISINTEGRATED".
*   **Environmental Transformation:** A wide range of static and dynamic materials are converted into "fire" across the entire game world.
*   **Persistent Flag:** A persistent flag `"secret_supernova"` is added to the game state.
*   **Self-Destruction:** The sun entity itself is destroyed after triggering the event.

## Key Attributes & Elements

*   **`entity_id`**: The unique identifier for the sun entity.
*   **`x`, `y`**: The current coordinates of the sun entity.
*   **`targets`**: A table containing entities within a 180-unit radius tagged with `"seed_f"`.
*   **`players`**: A table containing all entities tagged with `"player_unit"`.
*   **`mortals`**: A table containing all entities tagged with `"mortal"`.
*   **`EntityLoad("data/entities/particles/supernova.xml", x, y)`**: Spawns the visual supernova effect.
*   **`GameScreenshake(100, x, y)`**: Triggers a screen shake of intensity 100 at the given coordinates.
*   **`GamePlaySound("data/audio/Desktop/misc.bank", "misc/sun/supernova", x, y)`**: Plays the supernova sound effect.
*   **`EntityInflictDamage(v, 500, "DAMAGE_CURSE", "$damage_supernova", "DISINTEGRATED", 0, 0, entity_id)`**: Inflicts curse damage on mortal entities.
*   **`ConvertMaterialEverywhere(source_material, target_material)`**: A function that converts all instances of `source_material` to `target_material` globally.
*   **`AddFlagPersistent("secret_supernova")`**: Sets a persistent game flag.
*   **`EntityKill(entity_id)`**: Destroys the specified entity.

## Material Conversion Summary

The script converts numerous static and dynamic materials to "fire". Key examples include:

| Source Material        | Target Material |
| :--------------------- | :-------------- |
| `rock_static`          | `fire`          |
| `sand_static`          | `fire`          |
| `snowrock_static`      | `fire`          |
| `templebrick_static`   | `fire`          |
| `steel_static`         | `fire`          |
| `lavarock_static`      | `fire`          |
| `sand_static_rainforest` | `fire`          |
| `cloud`                | `fire`          |
| `wood_static`          | `fire`          |
| `wood_static_vertical` | `fire`          |