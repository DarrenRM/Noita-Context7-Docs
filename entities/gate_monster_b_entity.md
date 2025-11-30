---
title: Gate Monster B Entity
category: entities
---

# Gate Monster B Entity

This document describes the `gate_monster_b.xml` entity, which defines a boss-type enemy in Noita. It inherits its base properties from `gate_monster_a.xml` and introduces specific visual and physical characteristics.

## Key Components and Attributes

### Base Entity Inheritance

*   **`<Base file="data/entities/animals/boss_gate/gate_monster_a.xml">`**: This indicates that `gate_monster_b` inherits all properties from `gate_monster_a.xml`, with subsequent components overriding or adding to the base.

### PhysicsAIComponent

This component governs the entity's movement and physics interactions.

*   **`target_vec_max_len="15.0"`**: Maximum length of the vector used to guide the entity's movement towards a target.
*   **`force_coeff="16.0"`**: Coefficient for applying force to the entity.
*   **`force_balancing_coeff="1.6"`**: Coefficient for balancing forces, likely related to stability.
*   **`force_max="150"`**: Maximum force that can be applied to the entity.
*   **`torque_coeff="55"`**: Coefficient for applying rotational force (torque).

### PhysicsImageShapeComponent

Defines the visual representation and collision shape of the entity.

*   **`image_file="data/entities/animals/boss_gate/gate_monster_b.png"`**: Specifies the primary image file for the entity's sprite.
*   **`offset_x="18"`**: Horizontal offset for the image.
*   **`offset_y="35"`**: Vertical offset for the image.

### CharacterDataComponent

Contains core character-related data, including collision bounds and mass.

*   **`collision_aabb_min_x="-17"`**: Minimum X-coordinate for the Axis-Aligned Bounding Box (AABB) used for collision detection.
*   **`collision_aabb_max_x="17"`**: Maximum X-coordinate for the AABB.
*   **`collision_aabb_min_y="-35"`**: Minimum Y-coordinate for the AABB.
*   **`collision_aabb_max_y="35"`**: Maximum Y-coordinate for the AABB.
*   **`mass="1.8"`**: The mass of the entity, affecting its physics.

### SpriteParticleEmitterComponent (Shadow)

This component is used to create a visual effect, specifically a shadow.

*   **`sprite_file="data/entities/animals/boss_gate/gate_monster_b_glow.xml"`**: Specifies the sprite file used for the particle effect (likely a glow or shadow sprite).
*   **`randomize_position.min_x="0"`**: Minimum X-randomization for particle positions.
*   **`randomize_position.max_x="0"`**: Maximum X-randomization for particle positions.
*   **`randomize_position.min_y="-12"`**: Minimum Y-randomization for particle positions.
*   **`randomize_position.max_y="-12"`**: Maximum Y-randomization for particle positions. This setup suggests the particles are emitted at a fixed vertical offset relative to the entity, creating a consistent shadow effect.