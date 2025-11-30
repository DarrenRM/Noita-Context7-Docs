---
title: Fog of War Hole Particle
category: entities
---

# Fog of War Hole Particle

This entity defines a particle effect used to create "holes" in the fog of war, revealing areas of the map.

## Key Components

### SpriteComponent

This component handles the visual representation of the particle.

| Attribute      | Description                                                              |
|----------------|--------------------------------------------------------------------------|
| `alpha`        | Controls the transparency of the particle (0.55 means 55% opaque).       |
| `image_file`   | Specifies the image file used for the sprite. In this case, it's self-referential. |
| `smooth_filtering` | Enables smooth filtering for the sprite, reducing pixelation.          |
| `fog_of_war_hole` | **Crucial:** This attribute marks the sprite as a fog of war revealing element. |

### _Transform

This component handles the spatial transformation of the entity.

| Attribute | Description                                  |
|-----------|----------------------------------------------|
| `scale.x` | The scaling factor along the X-axis (1 means no scaling). |
| `scale.y` | The scaling factor along the Y-axis (1 means no scaling). |

## Usage

When this entity is spawned in the game, its `SpriteComponent` with `fog_of_war_hole="1"` will create a visible area, effectively clearing the fog of war in its location. The `alpha` value determines how "transparent" the revealed area is, allowing for subtle or more pronounced clearing.