---
title: Black Hole Big Custom Card
category: entities
---

# Black Hole Big Custom Card

This document describes the "Black Hole Big" custom card entity in Noita, focusing on its attributes relevant to AI-assisted modding.

## Entity Definition

The core of this entity is defined by its `Base` component, which inherits from `base_custom_card.xml`. This establishes it as a usable item within the game.

### Key Components

*   **`Base`**:
    *   **`SpriteComponent`**: Defines the visual representation of the card.
        *   `image_file`: `data/ui_gfx/gun_actions/black_hole_big.png` - Specifies the texture used for the card's icon.
    *   **`ItemActionComponent`**: Assigns an action ID to the card.
        *   `action_id`: `BLACK_HOLE_BIG` - This ID is crucial for referencing the card's functionality in game logic.
        *   `_tags`: `enabled_in_world` - Indicates the card is active and usable when found in the game world.

*   **`InheritTransformComponent`**: Controls the positioning of the card when held.
    *   `_tags`: `enabled_in_world,enabled_in_hand` - Ensures this component is active when the card is in the world and being held.
    *   **`Transform`**:
        *   `position.x`: `8`
        *   `position.y`: `0` - These values define the relative offset of the card's visual representation when held by the player.

*   **`ParticleEmitterComponent`**: Manages the visual particle effects associated with the card.
    *   `_tags`: `enabled_in_hand,item_identified` - The particles are active when the item is held and identified.
    *   `emitted_material_name`: `plasma_fading_pink` - The type of material used for the emitted particles.
    *   `offset.x`, `offset.y`: `0` - The center point for particle emission.
    *   `x_pos_offset_min`, `x_pos_offset_max`, `y_pos_offset_min`, `y_pos_offset_max`: Defines the area where particles can spawn around the offset.
    *   `x_vel_min`, `x_vel_max`, `y_vel_min`, `y_vel_max`: Controls the initial velocity of the emitted particles.
    *   `gravity.y`: `0.0` - Particles are not affected by gravity.
    *   `count_min`, `count_max`: `1`, `2` - The number of particles emitted per emission cycle.
    *   `lifetime_min`, `lifetime_max`: `0.1`, `0.6` - The duration each particle exists.
    *   `create_real_particles`: `0` - Indicates these are cosmetic particles, not physical entities.
    *   `emit_cosmetic_particles`: `1` - Confirms cosmetic particle emission.
    *   `emission_interval_min_frames`, `emission_interval_max_frames`: `3`, `5` - The delay between particle emission bursts.
    *   `is_emitting`: `1` - The particle emitter is active.

*   **`LightComponent`**: Adds a light source to the card.
    *   `_tags`: `enabled_in_hand,item_identified` - The light is active when the item is held and identified.
    *   `_enabled`: `1` - The light component is active.
    *   `radius`: `30` - The range of the light.
    *   `fade_out_time`: `1.5` - How long the light takes to fade.
    *   `r`, `g`, `b`: `80`, `10`, `80` - The RGB color values of the light, creating a purplish hue.