---
title: Medium Explosion Flare Fog of War Hole Particle
category: entities
---

# Medium Explosion Flare Fog of War Hole Particle

This entity defines a particle effect that creates a medium-sized hole in the fog of war, visually resembling an explosion flare.

## Key Components

### `_Transform`
This component controls the spatial properties of the entity.

| Attribute | Value | Description |
|---|---|---|
| `scale.x` | `10` | The horizontal scale of the particle. |
| `scale.y` | `10` | The vertical scale of the particle. |

### `SpriteComponent`
This component handles the visual representation of the particle.

| Attribute | Value | Description |
|---|---|---|
| `alpha` | `0.55` | The transparency of the sprite (0.0 is fully transparent, 1.0 is fully opaque). |
| `image_file` | `data/particles/explosion_flare_fog_of_war_hole.xml` | The image file used for the sprite. This likely references another particle definition for the visual flare itself. |
| `smooth_filtering` | `1` | Enables smooth filtering for the sprite, reducing pixelation. |
| `kill_entity_after_finished` | `1` | The entity will be automatically removed from the game once the sprite animation or effect is complete. |
| `fog_of_war_hole` | `1` | This crucial attribute indicates that this particle creates a hole in the fog of war. |