---
title: Gate Monster C Entity
category: entities
---

# Gate Monster C Entity

This document describes the `gate_monster_c.xml` entity, a variant of the Gate Monster boss. It inherits its base properties from `gate_monster_a.xml` and introduces specific visual and physical characteristics.

## Key Components and Attributes

### Base Entity Inheritance

*   **`<Base file="data/entities/animals/boss_gate/gate_monster_a.xml">`**: This entity inherits all properties from `gate_monster_a.xml`, indicating it shares fundamental behaviors and attributes with other Gate Monster variants.

### PhysicsAIComponent

This component governs the creature's movement and physics interactions.

*   **`target_vec_max_len="15.0"`**: Maximum length of the vector used to guide the creature towards its target.
*   **`force_coeff="19.0"`**: Coefficient for applying force, influencing movement speed and responsiveness.
*   **`force_max="130"`**: Maximum force that can be applied to the creature.
*   **`torque_coeff="55"`**: Coefficient for rotational forces, affecting how the creature turns.

### PhysicsImageShapeComponent

Defines the visual representation and collision shape of the entity.

*   **`image_file="data/entities/animals/boss_gate/gate_monster_c.png"`**: Specifies the primary image file used for the creature's sprite.
*   **`offset_x="18"`**: Horizontal offset for the sprite's origin.
*   **`offset_y="35"`**: Vertical offset for the sprite's origin.

### CharacterDataComponent

Contains core character-related data, including collision bounds and mass.

*   **`collision_aabb_min_x="-17"`**: Minimum X-coordinate for the Axis-Aligned Bounding Box (AABB) used for collision detection.
*   **`collision_aabb_max_x="17"`**: Maximum X-coordinate for the AABB.
*   **`collision_aabb_min_y="-35"`**: Minimum Y-coordinate for the AABB.
*   **`collision_aabb_max_y="35"`**: Maximum Y-coordinate for the AABB.
*   **`mass="1.8"`**: The mass of the creature, affecting its physics.

### SpriteParticleEmitterComponent (Shadow)

This component is used to create a visual effect, likely a shadow or glow.

*   **`sprite_file="data/entities/animals/boss_gate/gate_monster_c_glow.xml"`**: Specifies the sprite file for the particle effect.
*   **`randomize_position.min_y="-22"`**: Minimum Y-offset for the particle's position, suggesting it's positioned below the main sprite.
*   **`randomize_position.max_y="-22"`**: Maximum Y-offset for the particle's position.