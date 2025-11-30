---
title: Torch Item Entity
category: entities
---

# Torch Item Entity

This document details the `torch.xml` entity, which defines the behavior and appearance of the Torch item in Noita.

## Core Components

The Torch entity is built upon several core components that dictate its functionality:

### Base Custom Card

*   **`Base file="data/entities/base_custom_card.xml"`**: This indicates the Torch inherits properties from the generic custom card template, providing fundamental item behaviors.
*   **`SpriteComponent image_file="data/ui_gfx/gun_actions/torch.png"`**: Defines the visual representation of the Torch on the UI (e.g., in the inventory or hotbar).
*   **`ItemActionComponent action_id="TORCH"`**: Assigns a unique identifier to this item's action, allowing the game to recognize and trigger its specific functionality.

### Inherit Transform Component

*   **`InheritTransformComponent`**: This component is crucial for positioning the Torch when held by the player.
    *   **`Transform position.x="8" position.y="0"`**: Specifies the relative offset of the Torch from the player's hand.

## Visual Effects (Particle Emitters)

The Torch utilizes multiple `ParticleEmitterComponent` instances to create its visual effects, simulating fire, sparks, and smoke.

### Cosmetic Particle Emitters (Initial Burst)

These emitters create a more visually appealing, less impactful particle effect when the Torch is active.

*   **`emitted_material_name="spark"`**: Generates "spark" particles.
    *   **`count_min="1" count_max="2"`**: Emits 1 to 2 sparks per emission.
    *   **`lifetime_min="0.4" lifetime_max="0.6"`**: Sparks last between 0.4 and 0.6 seconds.
    *   **`create_real_particles="0"`**: These are cosmetic, not physical entities.
    *   **`emit_cosmetic_particles="1"`**: Explicitly marks these as cosmetic.
    *   **`emission_interval_min_frames="5" emission_interval_max_frames="15"`**: Sparks are emitted every 5 to 15 frames.
*   **`emitted_material_name="smoke"`**: Generates "smoke" particles with similar cosmetic settings.

### Real Particle Emitters (Fire and Smoke)

These emitters create physical particles that interact with the game world.

*   **`emitted_material_name="smoke"`**:
    *   **`create_real_particles="1"`**: These are physical smoke particles.
    *   **`emission_interval_min_frames="60" emission_interval_max_frames="250"`**: Smoke is emitted less frequently.
*   **`emitted_material_name="spark"`**:
    *   **`custom_style="FIRE"`**: Applies a specific "FIRE" style to the sparks.
    *   **`create_real_particles="1"`**: These are physical sparks.
    *   **`emission_interval_min_frames="1" emission_interval_max_frames="3"`**: Sparks are emitted very frequently.
*   **`emitted_material_name="fire"`**:
    *   **`create_real_particles="1"`**: These are physical fire particles.
    *   **`fire_cells_dont_ignite_damagemodel="1"`**: Prevents these fire particles from igniting other entities.

### Fog of War Component

*   **`SpriteComponent fog_of_war_hole="1"`**: This component creates a circular "hole" in the fog of war around the Torch, revealing the surrounding area.
    *   **`image_file="data/particles/torch_fog_of_war_hole.xml"`**: Specifies the visual asset for the fog of war effect.
    *   **`special_scale_x="4" special_scale_y="4"`**: Scales the fog of war effect to be larger.

## Lighting

The Torch emits light to illuminate the surroundings.

### Light Components

*   **`LightComponent radius="130" r="240" g="180" b="120"`**: Provides a larger, warm-toned light source.
*   **`LightComponent radius="16" r="255" g="255" b="255"`**: Provides a smaller, brighter white light source, likely for the core flame.

## Material Conversion

*   **`MagicConvertMaterialComponent`**: This component allows the Torch to interact with and potentially convert materials in its vicinity.
    *   **`temperature_reaction_temp="10"`**: Defines the temperature threshold for reactions.
    *   **`radius="7"`**: The area of effect for material conversion.
    *   **`loop="1"`**: The conversion process repeats.
    *   **`is_circle="1"`**: The area of effect is circular.
    *   **`InheritTransformComponent position.y="-3"`**: Positions this component relative to the Torch's main sprite.

## Audio

The Torch has associated sound effects.

### Audio Components

*   **`AudioComponent`**: Plays a sound event when the Torch is active.
    *   **`event_root="player_projectiles/torch"`**: The base event name for Torch sounds.
*   **`AudioLoopComponent`**: Plays a looping sound effect while the Torch is active.
    *   **`event_name="player_projectiles/torch/loop"`**: The specific looping sound event.
    *   **`auto_play_if_enabled="1"`**: The sound starts automatically when the component is enabled.