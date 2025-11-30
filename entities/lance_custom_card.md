---
title: Lance Custom Card
category: entities
---

# Lance Custom Card

This document details the configuration for the "Lance" custom card entity in Noita, intended for AI-assisted modding.

## Entity Definition

The core of this entity is defined by `<Entity>`, which inherits from a base custom card.

### Base Configuration

*   **`file="data/entities/base_custom_card.xml"`**: Inherits fundamental properties of a custom card.

### Sprite Component

Defines the visual representation of the card in the game's UI.

*   **`image_file="data/ui_gfx/gun_actions/lance.png"`**: Specifies the texture used for the card's icon.

### Item Action Component

Determines the action associated with this card when used.

*   **`action_id="LANCE"`**: Assigns the unique identifier for the "Lance" action.
*   **`_tags="enabled_in_world"`**: Ensures this action is available when the player is in the game world.

### Inherit Transform Component

Controls the positioning of the card's visual elements when held.

*   **`_tags="enabled_in_world,enabled_in_hand"`**: Applies these transformations when the card is in the world and held by the player.
*   **`Transform position.x="8"`**: Offsets the visual element 8 units to the right.
*   **`Transform position.y="0"`**: No vertical offset.

### Particle Emitter Component

Adds visual effects when the card is held and identified.

*   **`_tags="enabled_in_hand,item_identified"`**: Activates the particle emitter when the item is held and its identity is known.
*   **`emitted_material_name="spark_blue"`**: The type of particle to emit (blue sparks).
*   **`offset.x="0"`, `offset.y="0"`**: The center point for particle emission.
*   **`x_pos_offset_min="-2"`, `x_pos_offset_max="2"`**: Horizontal spread of emitted particles.
*   **`y_pos_offset_min="2"`, `y_pos_offset_max="-2"`**: Vertical spread of emitted particles.
*   **`x_vel_min="-2"`, `x_vel_max="2"`**: Horizontal velocity range of particles.
*   **`y_vel_min="-30"`, `y_vel_max="-10"`**: Vertical velocity range of particles (upwards).
*   **`count_min="1"`, `count_max="2"`**: Number of particles emitted per burst.
*   **`lifetime_min="0.4"`, `lifetime_max="0.6"`**: Duration each particle exists.
*   **`create_real_particles="0"`**: Particles are cosmetic, not physical entities.
*   **`emit_cosmetic_particles="1"`**: Enables the emission of cosmetic particles.
*   **`emission_interval_min_frames="5"`, `emission_interval_max_frames="15"`**: Controls the timing between particle bursts.
*   **`is_emitting="1"`**: The emitter is active by default.

### Light Component

Adds a dynamic light source when the card is held and identified.

*   **`_tags="enabled_in_hand,item_identified"`**: Activates the light when the item is held and identified.
*   **`_enabled="1"`**: The light component is enabled.
*   **`radius="30"`**: The radius of the light effect.
*   **`fade_out_time="1.5"`**: How long the light takes to fade out.
*   **`r="40"`, `g="140"`, `b="180"`**: The RGB color values for the light (a bluish hue).