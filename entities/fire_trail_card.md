---
title: Fire Trail Card
category: entities
---

# Fire Trail Card

This entity defines a custom wand card that creates a trail of sparks and smoke when fired. It's designed to be a visual effect rather than a damaging projectile.

## Key Components

### Base Entity (`<Base>`)

*   **`file="data/entities/base_custom_card.xml"`**: Inherits core functionality for custom cards.
*   **`SpriteComponent`**:
    *   `image_file="data/ui_gfx/gun_actions/fire_trail.png"`: Specifies the UI icon for this card.

### Item Action (`<ItemActionComponent>`)

*   **`action_id="FIRE_TRAIL"`**: Identifies this card's unique action.

### Inheritance (`<InheritTransformComponent>`)

*   **`position.x="8"`, `position.y="0"`**: Offsets the card's visual representation when held.

### Particle Emitters (`<ParticleEmitterComponent>`)

This card utilizes three `ParticleEmitterComponent`s to generate visual effects.

#### Emitter 1 (Cosmetic Sparks)

*   **`_tags="enabled_in_hand,item_identified"`**: Active when the card is held and identified.
*   **`emitted_material_name="spark"`**: The material used for the particles.
*   **`x_pos_offset_min="-2"`, `x_pos_offset_max="2"`**: Horizontal spread of emitted particles.
*   **`y_pos_offset_min="2"`, `y_pos_offset_max="-2"`**: Vertical spread of emitted particles.
*   **`x_vel_min="-2"`, `x_vel_max="2"`**: Horizontal velocity of particles.
*   **`y_vel_min="-20"`, `y_vel_max="-10"`**: Downward velocity of particles.
*   **`count_min="1"`, `count_max="2"`**: Number of particles emitted per burst.
*   **`lifetime_min="0.4"`, `lifetime_max="0.6"`**: Duration particles exist.
*   **`create_real_particles="0"`**: These are purely cosmetic.
*   **`emit_cosmetic_particles="1"`**: Enables cosmetic particle emission.
*   **`emission_interval_min_frames="5"`, `emission_interval_max_frames="15"`**: Frequency of particle bursts.
*   **`is_emitting="1"`**: The emitter is active.

#### Emitter 2 (Real Sparks)

*   **`_tags="enabled_in_hand,item_identified"`**: Active when the card is held and identified.
*   **`emitted_material_name="spark"`**: The material used for the particles.
*   **`count_min="1"`, `count_max="1"`**: Number of particles emitted per burst.
*   **`create_real_particles="1"`**: These particles can interact with the game world.
*   **`emission_interval_min_frames="15"`, `emission_interval_max_frames="25"`**: Frequency of particle bursts.

#### Emitter 3 (Smoke)

*   **`_tags="enabled_in_hand,item_identified"`**: Active when the card is held and identified.
*   **`emitted_material_name="smoke"`**: The material used for the particles.
*   **`count_min="1"`, `count_max="1"`**: Number of particles emitted per burst.
*   **`create_real_particles="1"`**: These particles can interact with the game world.
*   **`emission_interval_min_frames="15"`, `emission_interval_max_frames="30"`**: Frequency of particle bursts.

### Light Component (`<LightComponent>`)

*   **`_tags="enabled_in_hand,item_identified"`**: Active when the card is held and identified.
*   **`radius="30"`**: The radius of the light emitted.
*   **`fade_out_time="1.5"`**: How long the light takes to fade.
*   **`r="120"`, `g="80"`, `b="10"`**: Defines the warm, orange color of the light.