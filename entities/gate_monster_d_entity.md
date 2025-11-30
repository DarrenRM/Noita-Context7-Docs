---
title: Gate Monster D Entity
category: entities
---

# Gate Monster D Entity

This document describes the `gate_monster_d.xml` entity, a variant of the boss gate monster in Noita. It inherits its base properties from `gate_monster_a.xml` and introduces specific visual and physical characteristics.

## Key Components

### Base Entity

*   **`name`**: `$animal_gate_monster_d` - The internal name for this entity.
*   **`Base file`**: `data/entities/animals/boss_gate/gate_monster_a.xml` - Inherits core behaviors and properties from the base gate monster.

### PhysicsAIComponent

This component governs the entity's movement and physics interactions.

*   **`target_vec_max_len`**: `16.0` - Maximum length of the vector used to guide the entity's movement towards a target.
*   **`force_coeff`**: `19.0` - Coefficient for applying force to the entity.
*   **`force_max`**: `180` - Maximum force that can be applied.
*   **`torque_coeff`**: `55` - Coefficient for applying rotational force.

### PhysicsImageShapeComponent

Defines the visual representation and collision shape of the entity.

*   **`image_file`**: `data/entities/animals/boss_gate/gate_monster_d.png` - The primary sprite for this entity.
*   **`offset_x`**: `18` - Horizontal offset for the sprite.
*   **`offset_y`**: `35` - Vertical offset for the sprite.

### CharacterDataComponent

Contains data related to the character's physical properties and collision.

*   **`collision_aabb_min_x`**: `-28` - Minimum X-coordinate for the Axis-Aligned Bounding Box (AABB) collision.
*   **`collision_aabb_max_x`**: `28` - Maximum X-coordinate for the AABB collision.
*   **`collision_aabb_min_y`**: `-28` - Minimum Y-coordinate for the AABB collision.
*   **`collision_aabb_max_y`**: `28` - Maximum Y-coordinate for the AABB collision.
*   **`mass`**: `1.8` - The mass of the entity.

### SpriteParticleEmitterComponent (Shadow)

This component is used to emit particles, specifically for a shadow effect.

*   **`sprite_file`**: `data/entities/animals/boss_gate/gate_monster_d_glow.xml` - Specifies the sprite used for the emitted particles (likely a glow or shadow effect).
*   **`randomize_position.min_y`**: `-12` - Minimum vertical randomization for particle emission.
*   **`randomize_position.max_y`**: `-12` - Maximum vertical randomization for particle emission.