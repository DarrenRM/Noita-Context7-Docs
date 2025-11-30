---
title: Runestone Metal Entity
category: entities
---

# Runestone Metal Entity

This document describes the `runestone_metal.xml` entity, which defines the in-game item "Runestone Metal" in Noita. It inherits base properties from `runestone_base.xml` and adds specific visual and functional elements.

## Key Components and Attributes

This entity primarily focuses on its visual representation and its role as a pickup item.

### Base Entity

*   **`Base file="data/entities/items/pickup/runestones/runestone_base.xml"`**: Inherits core functionality and properties from the generic runestone base entity.

### Physics and Visuals

*   **`PhysicsImageShapeComponent`**:
    *   `image_file="data/items_gfx/runestones/runestone_metal.png"`: Specifies the primary image used for the runestone's physics shape and visual representation in the game world.
*   **`SpriteComponent`**:
    *   `image_file="data/items_gfx/in_hand/runestone_metal.png"`: Defines the sprite used when the runestone is held by the player.

### Item and UI Information

*   **`ItemComponent`**:
    *   `item_name="$item_runestone_metal"`: The internal name for the item, used for referencing in code and localization.
    *   `ui_sprite="data/ui_gfx/items/runestone_metal.png"`: The sprite displayed in the player's inventory and UI.
    *   `ui_description="$itemdesc_runestone"`: The localized description text for the item.
*   **`UIInfoComponent`**:
    *   `name="$item_runestone_metal"`: Provides the name displayed in UI elements.
*   **`AbilityComponent`**:
    *   `ui_name="$item_runestone_metal"`: Used for displaying the item's name in ability-related UI.

### Particle Effects

*   **`ParticleEmitterComponent`**:
    *   `_tags="activate"`: This component is activated under specific conditions.
    *   `_enabled="0"`: The particle emitter is initially disabled.
    *   `emitted_material_name="smoke"`: The type of particle emitted is "smoke".
    *   `lifetime_min="10.01"`, `lifetime_max="10.1"`: Particles have a very short lifespan.
    *   `count_min="200"`, `count_max="200"`: Emits a fixed number of particles.
    *   `area_circle_radius.min="16"`, `area_circle_radius.max="16"`: Particles are emitted within a circular area.
    *   `cosmetic_force_create="1"`: Ensures particles are created even if other conditions aren't met.
    *   `airflow_force="0.551"`, `airflow_time="1.01"`, `airflow_scale="0.05"`: Defines airflow properties affecting particle movement.
    *   `emission_interval_min_frames="55"`, `emission_interval_max_frames="55"`: Particles are emitted at a fixed interval.
    *   `velocity_always_away_from_center="120"`: Particles are propelled outwards from the emission center.
    *   `collide_with_grid="0"`: Particles do not interact with the game grid.

### Lua Scripting

*   **`LuaComponent`**:
    *   `_tags="activate"`: This component is activated under specific conditions.
    *   `script_source_file="data/scripts/items/runestones/runestone_metal.lua"`: Links to the Lua script that defines the runestone's behavior and effects.
    *   `execute_every_n_frame="60"`: The script logic executes every 60 frames.
    *   `_enabled="0"`: The Lua script is initially disabled.

## Summary

The `runestone_metal.xml` entity defines a pickup item in Noita. It is visually represented by specific sprites and has associated UI information. While it has a particle emitter for cosmetic effects and a Lua script for potential functionality, these are initially disabled, suggesting their activation is tied to game events or player interaction. The core purpose is to serve as a collectible item with a defined appearance and name.