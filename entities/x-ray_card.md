---
title: X-Ray Card
category: entities
---

# X-Ray Card

This document describes the `xray.xml` entity, which defines the X-Ray wand in Noita. This wand provides the player with the ability to see through walls and other obstacles.

## Base Entity

The X-Ray card inherits from `base_custom_card.xml`, which provides fundamental properties for custom wand cards.

### Key Components:

*   **`Base file="data/entities/base_custom_card.xml"`**: Inherits core functionality for custom cards.
*   **`SpriteComponent`**:
    *   `image_file="data/ui_gfx/gun_actions/x_ray.png"`: Specifies the visual representation of the X-Ray wand on the UI.
*   **`ItemActionComponent`**:
    *   `action_id="X_RAY"`: Assigns the unique identifier for the X-Ray action.
    *   `_tags="enabled_in_world"`: Ensures the action is available when the item is in the game world.

## Visual and Functional Enhancements

These components add visual effects and define the behavior of the X-Ray wand when held by the player.

### Key Components:

*   **`InheritTransformComponent`**:
    *   `_tags="enabled_in_world,enabled_in_hand"`: Applies transformations when the item is in the world and held.
    *   `Transform position.x="8" position.y="0"`: Defines the relative position of the wand's sprite when held.
*   **`ParticleEmitterComponent`**:
    *   `_tags="enabled_in_hand,item_identified"`: Activates particle effects when the wand is held and identified.
    *   `emitted_material_name="plasma_fading_pink"`: Sets the material for the emitted particles.
    *   `count_min="1" count_max="2"`: Controls the number of particles emitted per burst.
    *   `lifetime_min="0.1" lifetime_max="0.6"`: Determines the lifespan of individual particles.
    *   `emission_interval_min_frames="5" emission_interval_max_frames="15"`: Sets the delay between particle emission bursts.
    *   `emit_cosmetic_particles="1"`: Indicates that these are visual, non-damaging particles.
*   **`LightComponent`**:
    *   `_tags="enabled_in_hand,item_identified"`: Activates the light effect when the wand is held and identified.
    *   `radius="30"`: Defines the range of the light emitted.
    *   `fade_out_time="1.5"`: Controls how long the light takes to fade.
    *   `r="80" g="10" b="80"`: Sets the color of the light to a purplish hue.