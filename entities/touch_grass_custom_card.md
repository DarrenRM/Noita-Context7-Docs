---
title: Touch Grass Custom Card
category: entities
---

# Touch Grass Custom Card

This document describes the "Touch Grass" custom card entity in Noita, designed for AI-assisted modding.

## Entity Definition

The `touch_grass.xml` file defines a custom card entity that, when used, triggers a specific action and visual effect.

### Key Components

*   **`<Base file="data/entities/base_custom_card.xml">`**: Inherits core functionality from the base custom card entity.
    *   **`<SpriteComponent>`**: Defines the visual representation of the card in the UI.
        *   `image_file`: `data/ui_gfx/gun_actions/touch_grass.png` - Specifies the sprite used for the card.
    *   **`<ItemActionComponent>`**: Assigns an action ID to the card.
        *   `action_id`: `TOUCH_GRASS` - The unique identifier for this card's action.
        *   `_tags="enabled_in_world"`: Indicates the action is available when the card is in the game world.

*   **`<InheritTransformComponent>`**: Manages the card's position relative to its parent.
    *   `_tags="enabled_in_world,enabled_in_hand"`: The transform is active when the card is in the world or held.
    *   **`<Transform>`**: Defines the relative position.
        *   `position.x="8"`
        *   `position.y="0"`

*   **`<ParticleEmitterComponent>`**: Controls the visual particle effects when the card is activated.
    *   `_tags="enabled_in_hand,enabled_in_world"`: Particles are emitted when the card is held or in the world.
    *   `emitted_material_name="spark_green"`: The type of particle to emit.
    *   `gravity.y="10"`: Controls the particle's vertical acceleration.
    *   `x_pos_offset_min`, `x_pos_offset_max`, `y_pos_offset_min`, `y_pos_offset_max`: Define the area where particles are spawned.
    *   `x_vel_min`, `x_vel_max`, `y_vel_min`, `y_vel_max`: Control the initial velocity of the particles.
    *   `count_min`, `count_max`: The number of particles emitted per burst.
    *   `lifetime_min`, `lifetime_max`: The duration particles exist.
    *   `render_on_grid="1"`: Particles are rendered on the game grid.
    *   `fade_based_on_lifetime="1"`: Particles fade out as their lifetime ends.
    *   `create_real_particles="0"`: These are cosmetic particles, not physical entities.
    *   `emit_cosmetic_particles="1"`: Explicitly marks these as cosmetic.
    *   `emission_interval_min_frames`, `emission_interval_max_frames`: Controls the timing between particle emissions.
    *   `is_emitting="1"`: The particle emitter is active.

*   **`<VariableStorageComponent>`**: A component for storing variables, though it's disabled (`_enabled="0"`) in this configuration.
    *   `_tags="enabled_in_hand"`: Would be active when the card is held.

*   **`<LuaComponent>`**: Links the entity to a Lua script for custom logic.
    *   `_tags="enabled_in_hand,enabled_in_world"`: The script executes when the card is held or in the world.
    *   `script_source_file="data/scripts/projectiles/touch_grass.lua"`: The path to the associated Lua script.
    *   `execute_every_n_frame="20"`: The script's `update` function will be called every 20 frames.

## Lua Scripting

The `touch_grass.lua` script (located at `data/scripts/projectiles/touch_grass.lua`) contains the actual logic executed when the "Touch Grass" card is used. This script is responsible for defining what happens when the `TOUCH_GRASS` action is triggered.

### Key Script Functionality (Assumed based on `execute_every_n_frame`)

*   **`update(entity, game_state)`**: This function is likely called every 20 frames. It would contain the core logic for the "Touch Grass" effect.
*   **Potential Actions**: The script might:
    *   Apply a status effect to the player.
    *   Spawn specific entities or particles.
    *   Modify player stats or game state.
    *   Trigger unique environmental interactions.

## Usage Notes for Modders

*   **Customization**: To modify the "Touch Grass" effect, edit the `touch_grass.lua` script.
*   **Visuals**: Change the `image_file` in the `SpriteComponent` to alter the card's appearance. Adjust `emitted_material_name` and particle parameters in the `ParticleEmitterComponent` for different visual effects.
*   **Action ID**: The `action_id` is crucial for how the game recognizes and triggers this card's functionality.
*   **Tags**: Pay attention to `_tags` to ensure components and scripts activate in the intended game states (e.g., `enabled_in_world`, `enabled_in_hand`).