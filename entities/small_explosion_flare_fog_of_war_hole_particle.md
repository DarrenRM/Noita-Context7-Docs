---
title: Small Explosion Flare Fog of War Hole Particle
category: entities
---

# Small Explosion Flare Fog of War Hole Particle

This entity defines a small particle effect that creates a temporary hole in the fog of war, simulating a brief flare or explosion.

## Key Components

### `_Transform`
This component controls the spatial properties of the entity.

| Attribute | Value | Description |
|---|---|---|
| `scale.x` | 10 | Scales the entity horizontally. |
| `scale.y` | 10 | Scales the entity vertically. |

### `SpriteComponent`
This component handles the visual representation of the particle.

| Attribute | Value | Description |
|---|---|---|
| `alpha` | 0.55 | Controls the transparency of the sprite (0.0 is fully transparent, 1.0 is fully opaque). |
| `image_file` | `data/particles/explosion_flare_fog_of_war_hole_small.xml` | Specifies the image file used for the sprite. |
| `smooth_filtering` | 1 | Enables smooth filtering for the sprite, reducing pixelation. |
| `kill_entity_after_finished` | 1 | Ensures the entity is removed from the game once its visual effects are complete. |
| `fog_of_war_hole` | 1 | **Crucial attribute:** This flag makes the particle create a temporary hole in the fog of war. |