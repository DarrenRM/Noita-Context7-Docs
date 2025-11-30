---
title: Fog of War Hole Explosion Flare Particle
category: entities
---

# Fog of War Hole Explosion Flare Particle

This entity defines a particle effect that creates a temporary hole in the fog of war, simulating an explosion flare.

## Key Components

### `_Transform`
This component controls the spatial properties of the entity.

| Attribute | Value | Description |
|---|---|---|
| `scale.x` | 15 | Scales the entity by 15 units on the X-axis. |
| `scale.y` | 15 | Scales the entity by 15 units on the Y-axis. |

### `SpriteComponent`
This component handles the visual representation of the particle.

| Attribute | Value | Description |
|---|---|---|
| `alpha` | 0.55 | Sets the transparency of the sprite to 55%. |
| `image_file` | `data/particles/explosion_flare_fog_of_war_hole.xml` | Specifies the image file used for the sprite. |
| `smooth_filtering` | 1 | Enables smooth filtering for the sprite, reducing pixelation. |
| `kill_entity_after_finished` | 1 | The entity will be automatically removed from the game once its animation or effect is complete. |
| `fog_of_war_hole` | 1 | This crucial attribute makes the sprite create a hole in the fog of war. |