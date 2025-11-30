---
title: White Hole Giga Custom Card
category: entities
---

# White Hole Giga Custom Card

This document details the `white_hole_giga.xml` entity, representing a custom spell card in Noita.

## Entity Definition

The core of this entity is defined by `<Entity>`, which contains several components that dictate its behavior and appearance.

### Base Components

*   **`<Base file="data/entities/base_custom_card.xml">`**: This indicates that the entity inherits fundamental properties from the `base_custom_card.xml` file. This is crucial for defining it as a usable spell card.
    *   **`<SpriteComponent image_file="data/ui_gfx/gun_actions/white_hole_giga.png">`**: Defines the visual representation of the card in the game's UI, specifically its icon when held or in the inventory.

### Item Action Component

*   **`<ItemActionComponent action_id="WHITE_HOLE_GIGA">`**: This component assigns a unique identifier to the action performed when this card is used. `WHITE_HOLE_GIGA` signifies the specific spell effect.
    *   **`_tags="enabled_in_world"`**: This tag ensures the card is active and usable within the game world.

### Transform Component

*   **`<InheritTransformComponent _tags="enabled_in_world,enabled_in_hand">`**: This component manages the spatial positioning and orientation of the card.
    *   **`<Transform position.x="8" position.y="0">`**: Sets a relative offset for the card when it's in the player's hand or in the world.

### Particle Emitter Component

*   **`<ParticleEmitterComponent _tags="enabled_in_hand,item_identified">`**: This component is responsible for generating visual particle effects associated with the card.
    *   **`emitted_material_name="spark_white"`**: Specifies the type of material used for the emitted particles.
    *   **`offset.x="0" offset.y="0"`**: The origin point for particle emission.
    *   **`x_pos_offset_min/max`, `y_pos_offset_min/max`**: Defines the area within which particles can spawn.
    *   **`x_vel_min/max`, `y_vel_min/max`**: Controls the initial velocity of the spawned particles.
    *   **`gravity.y="0.0"`**: Particles are not affected by gravity.
    *   **`count_min/max`**: The number of particles emitted per burst.
    *   **`lifetime_min/max`**: The duration each particle exists.
    *   **`create_real_particles="0"`**: Indicates that these are cosmetic particles, not physical entities.
    *   **`emit_cosmetic_particles="1"`**: Confirms that cosmetic particles are indeed emitted.
    *   **`emission_interval_min/max_frames`**: Controls the timing between particle emission bursts.
    *   **`is_emitting="1"`**: Ensures the particle emitter is active.

### Light Component

*   **`<LightComponent _tags="enabled_in_hand,item_identified" _enabled="1">`**: This component adds a light source to the entity.
    *   **`radius="40"`**: The range of the light.
    *   **`fade_out_time="1.5"`**: How long it takes for the light to fade out.
    *   **`r="80" g="80" b="80"`**: The color of the light (a dim white/grey).