---
title: Forge Item Converter Building
category: entities
---

# Forge Item Converter Building

This entity represents a building in Noita that converts items. It utilizes particle effects for visual feedback during its buildup and has a Lua script to handle its conversion logic.

## Key Components

### ParticleEmitterComponent
This component manages the visual buildup effect of the forge.

*   **emitted_material_name**: `spark_purple` - The material used for the emitted particles.
*   **lifetime\_min/max**: `0.8` / `5.5` - The minimum and maximum lifetime of individual particles.
*   **count\_min/max**: `20` / `40` - The minimum and maximum number of particles emitted per interval.
*   **render\_on\_grid**: `1` - Ensures the particles are rendered on the game grid.
*   **fade\_based\_on\_lifetime**: `1` - Particles fade out as their lifetime decreases.
*   **emission\_interval\_min/max\_frames**: `1` / `1` - Particles are emitted every frame.
*   **image\_animation\_file**: `data/particles/image_emitters/circle_reverse_64.png` - The animation file for the particles.
*   **image\_animation\_speed**: `3.5` - The speed of the particle animation.

### LuaComponent
This component executes the core logic for the item conversion.

*   **script\_source\_file**: `data/scripts/buildings/forge_item_convert.lua` - The path to the Lua script that defines the building's behavior.
*   **execute\_every\_n\_frame**: `80` - The script logic runs every 80 frames.

### LifetimeComponent
Determines how long the building persists.

*   **lifetime**: `81` - The building will exist for 81 frames.

### AudioComponent
Handles the sound effects associated with the building.

*   **file**: `data/audio/Desktop/projectiles.snd` - The sound file used.
*   **event\_root**: `player_projectiles/crumbling_earth` - The specific audio event triggered.