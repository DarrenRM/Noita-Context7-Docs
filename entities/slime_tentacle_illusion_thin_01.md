---
title: Slime Tentacle Illusion Thin 01
category: entities
---

---

# Slime Tentacle Illusion Thin 01

This entity defines a thin, illusory slime tentacle segment used in Noita. It inherits its core functionality from `slime_tentacle_piece_thin.xml` and applies a transparency effect.

## Key Components

### VerletPhysicsComponent

This component governs the physics simulation of the tentacle, allowing it to behave like a chain of connected points.

| Attribute           | Value   | Description                                                                 |
| :------------------ | :------ | :-------------------------------------------------------------------------- |
| `stiffness`         | `1.25`  | Controls how rigid the tentacle segments are. Higher values mean less bend. |
| `num_points`        | `7`     | The number of points that make up the tentacle chain.                       |
| `velocity_dampening`| `0.8`   | Reduces the velocity of the tentacle points over time, simulating friction. |
| `resting_distance`  | `1.0`   | The preferred distance between connected points when not under tension.     |

### Base (Inheritance)

The entity inherits its visual and functional base from `slime_tentacle_piece_thin.xml`.

*   **Multiple `<Base>` tags:** The presence of multiple identical `<Base>` tags, each with a `<SpriteComponent alpha="0.5" />`, suggests that this specific illusion variant might be composed of multiple overlapping or layered tentacle pieces, each with reduced opacity.

### SpriteComponent (Applied via Inheritance)

Each inherited `slime_tentacle_piece_thin.xml` has its `SpriteComponent` modified to have an `alpha` value of `0.5`.

*   `alpha`: `0.5` - This makes the tentacle appear semi-transparent or "illusory."