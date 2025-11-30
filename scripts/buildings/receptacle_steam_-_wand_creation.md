---
title: Receptacle Steam - Wand Creation
category: scripts/buildings
---

# Receptacle Steam - Wand Creation

This script defines the behavior for a "receptacle" entity that, upon successful material detection, spawns a specific wand and particle effect, accompanied by a sound.

## Core Functionality

The primary function `material_area_checker_success` is triggered when the entity successfully identifies a material within its area.

### Key Actions

*   **Wand Spawning:** Loads `data/entities/items/wand_kiekurakeppi.xml` at a position slightly above the entity.
*   **Particle Effect:** Loads `data/entities/particles/image_emitters/magical_symbol.xml` at the same position.
*   **Sound Playback:** Plays the sound `data/audio/Desktop/projectiles.snd` with the event `player_projectiles/crumbling_earth/create` at the entity's location.
*   **Self-Destruction:** The entity that triggered this function is then killed using `EntityKill(entity_id)`.

## Dependencies

*   `dofile_once("data/scripts/lib/utilities.lua")`: Imports utility functions.

## Entity Loading

The script utilizes `EntityLoad` to instantiate other game entities.

### Spawned Entities

*   **Wand:** `data/entities/items/wand_kiekurakeppi.xml`
*   **Particle Emitter:** `data/entities/particles/image_emitters/magical_symbol.xml`

## Sound Events

A specific sound event is triggered upon successful material detection.

### Sound Details

*   **Sound File:** `data/audio/Desktop/projectiles.snd`
*   **Event Name:** `player_projectiles/crumbling_earth/create`