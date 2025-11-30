---
title: Frozen Effect (Short Duration)
category: entities
---

# Frozen Effect (Short Duration)

This entity defines a short-duration freezing effect applied to entities in Noita.

## Key Components

### GameEffectComponent
This component dictates the primary behavior of the effect.

*   **`effect`**: `FROZEN` - Specifies the type of game effect.
*   **`frames`**: `50` - The duration of the effect in game frames (approximately 0.83 seconds).
*   **`disable_movement`**: `1` - When active, this prevents the affected entity from moving.
*   **`ragdoll_effect`**: `FROZEN` - The effect applied to the entity's ragdoll when it's frozen.
*   **`ragdoll_material`**: `ice_glass_b2` - The material assigned to the ragdoll when frozen, influencing its visual appearance and physics.