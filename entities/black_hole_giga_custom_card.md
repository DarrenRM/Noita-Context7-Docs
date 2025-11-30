---
title: Black Hole Giga Custom Card
category: entities
---

# Black Hole Giga Custom Card

This document details the `black_hole_giga.xml` entity, which defines a custom spell card in Noita. This card, when acquired, grants the player the "Black Hole Giga" spell.

## Key Components

### Base Entity (`<Base>`)

This element inherits from `base_custom_card.xml`, providing the fundamental structure for a custom spell card.

*   **`<SpriteComponent>`**: Defines the visual representation of the card in the UI.
    *   `image_file`: `data/ui_gfx/gun_actions/black_hole_giga.png` - Specifies the texture used for the card's icon.

*   **`<ItemActionComponent>`**: Links the card to a specific game action.
    *   `_tags`: `enabled_in_world` - Indicates the card is active and usable within the game world.
    *   `action_id`: `BLACK_HOLE_GIGA` - The unique identifier for the spell action this card triggers.

### Transform (`<InheritTransformComponent>`)

This component dictates the card's position relative to the player's hand when held.

*   `_tags`: `enabled_in_world,enabled_in_hand` - Ensures the transform is applied when the card is in the world and held by the player.
*   **`<Transform>`**:
    *   `position.x`: `8` - Offset on the X-axis.
    *   `position.y`: `0` - Offset on the Y-axis.

### Visual Effects (`<ParticleEmitterComponent>`)

This component generates cosmetic particles to enhance the visual flair of the card when held.

*   `_tags`: `enabled_in_hand,item_identified` - Particles are emitted when the card is held and has been identified by the player.
*   `emitted_material_name`: `plasma_fading_pink` - The material used for the emitted particles.
*   `offset.x`, `offset.y`: `0` - The center point for particle emission.
*   `x_pos_offset_min`, `x_pos_offset_max`, `y_pos_offset_min`, `y_pos_offset_max`: Defines a small area around the offset from which particles can spawn.
*   `x_vel_min`, `x_vel_max`, `y_vel_min`, `y_vel_max`: Sets the initial velocity range for the particles.
*   `gravity.y`: `0.0` - Particles are not affected by gravity.
*   `count_min`, `count_max`: `1`, `2` - The number of particles emitted per emission cycle.
*   `lifetime_min`, `lifetime_max`: `0.1`, `0.6` - The duration each particle exists.
*   `create_real_particles`: `0` - These are cosmetic particles, not physical entities.
*   `emit_cosmetic_particles`: `1` - Explicitly states that cosmetic particles are emitted.
*   `emission_interval_min_frames`, `emission_interval_max_frames`: `1`, `2` - Controls how frequently particles are emitted.
*   `is_emitting`: `1` - The particle emitter is active.

### Lighting (`<LightComponent>`)

This component adds a light source around the card when held, enhancing its visual presence.

*   `_tags`: `enabled_in_hand,item_identified` - The light is active when the card is held and identified.
*   `_enabled`: `1` - The light component is active.
*   `radius`: `40` - The range of the light.
*   `fade_out_time`: `1.5` - How long it takes for the light to fade.
*   `r`, `g`, `b`: `80`, `10`, `80` - Defines the color of the light (a purplish hue).