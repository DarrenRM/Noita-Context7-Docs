---
title: Physics Worm Deflector Base
category: entities
---

# Physics Worm Deflector Base

This entity defines the base properties for a physics-based worm deflector. It's designed to interact with the game's physics engine and can be destroyed.

## Key Components

### Base Entity

*   **`Base file="data/entities/base_item_physics.xml"`**: Inherits core physics item functionalities.

### Physics Body Component

*   **`on_death_leave_physics_body="1"`**: Ensures that the physics body remains in the world even after the entity is destroyed, allowing for potential interactions or visual remnants.

### Physics Image Shape Component

*   **`image_file="data/props_gfx/worm_deflector_base.png"`**: Specifies the visual asset used for the deflector.
*   **`material="metal_prop"`**: Assigns a material property, likely influencing its physical interactions and appearance.

## Destruction Properties

While not explicitly defined as direct attributes in this snippet, the comments indicate potential for destruction behavior:

*   **`physics_body_destruction_required`**: A threshold (0.0-1.0) determining how much the physics body needs to be destroyed before triggering further effects.
*   **`physics_body_modified_death_probability`**: If the destruction level exceeds `physics_body_destruction_required`, this value (0.0-1.0) dictates the probability of the entity exploding.