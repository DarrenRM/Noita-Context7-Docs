---
title: Knockback Particle Entity
category: entities/particles
---

# Knockback Particle Entity

This entity defines the visual and behavioral components for a knockback particle effect in Noita. It's designed to be a visual indicator that accompanies a knockback action.

## Key Components

### InheritTransformComponent

*   **`only_position="1"`**: This indicates that the particle will only inherit the position of its parent entity, not its rotation or scale.

### SpriteComponent

This component handles the visual representation of the particle.

*   **`_tags="fx"`**: Marks this component as a visual effect.
*   **`_enabled="0"`**: The sprite is initially disabled, likely controlled by the Lua script.
*   **`image_file="data/particles/knockback_star_spinning.xml"`**: Specifies the image file used for the particle's appearance. This points to another XML file that defines the sprite's animation and frames.
*   **`additive="1"`**: The sprite uses additive blending, meaning its colors are added to the background, creating a brighter effect.
*   **`emissive="1"`**: The sprite emits light, contributing to its brightness.
*   **`alpha="1"`**: The particle is fully opaque.
*   **`z_index="-1.2"`**: Sets the drawing order. A negative value places it behind most other elements.

### LuaComponent

This component controls the particle's behavior through a Lua script.

*   **`_tags="fx"`**: Marks this component as a visual effect.
*   **`_enabled="0"`**: The Lua script is initially disabled, likely controlled by the entity that spawns this particle.
*   **`script_source_file="data/scripts/particles/knockback.lua"`**: The path to the Lua script that governs the particle's logic.
*   **`execute_every_n_frame="4"`**: The script will execute its logic every 4 frames, controlling the particle's animation or movement over time.