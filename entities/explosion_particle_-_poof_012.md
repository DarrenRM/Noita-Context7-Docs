---
title: Explosion Particle - Poof 012
category: guides
---

<ParticleAction 
  action="SPAWN" 
  count="1" 
  entity_file="data/entities/particles/explosion_012_poof.xml" 
  spawn_direction="0" 
  spawn_radius="0" >
</ParticleAction>
```

```xml
<Particle 
  anim="explosion" 
  frame_count="6" 
  frame_height="13" 
  frame_wait="0.06" 
  frame_width="13" 
  frames_per_row="6" 
  loop="0" 
  name="explosion" 
  pos_x="0" 
  pos_y="1" 
  shrink_by_one_pixel="1" 
  sprite_file="data/particles/explosion_012_poof.png" >
</Particle>
```

---
title: Explosion Particle - Poof 012
category: particles
---

# Explosion Particle - Poof 012

This documentation describes the `explosion_012_poof.xml` file, which defines a small, poof-like explosion particle effect in Noita.

## Sprite Definition

The `Sprite` element defines the visual appearance and animation of the particle.

### Key Attributes:

*   **`default_animation`**: "explosion" - Specifies the default animation to play.
*   **`filename`**: "data/particles/explosion_012_poof.png" - The texture file used for the sprite.
*   **`offset_x`**: "6" - Horizontal offset for the sprite.
*   **`offset_y`**: "6" - Vertical offset for the sprite.

### RectAnimation Element:

This nested element defines the specific animation frames.

#### Key Attributes:

*   **`name`**: "explosion" - The name of this animation.
*   **`frame_count`**: "6" - The total number of frames in the animation.
*   **`frame_width`**: "13" - The width of each individual frame.
*   **`frame_height`**: "13" - The height of each individual frame.
*   **`frames_per_row`**: "6" - How many frames are arranged horizontally in the sprite sheet.
*   **`frame_wait`**: "0.06" - The duration (in seconds) each frame is displayed before advancing.
*   **`loop`**: "0" - Indicates that the animation does not loop (plays once).
*   **`pos_x`**: "0" - X-coordinate of the animation's top-left corner within the sprite sheet.
*   **`pos_y`**: "1" - Y-coordinate of the animation's top-left corner within the sprite sheet.
*   **`shrink_by_one_pixel`**: "1" - A flag that causes the sprite to shrink by one pixel each frame.

## Particle Action

The `ParticleAction` element defines what happens when this particle is spawned.

### Key Attributes:

*   **`action`**: "SPAWN" - The type of action to perform.
*   **`count`**: "1" - The number of entities to spawn.
*   **`entity_file`**: "data/entities/particles/explosion_012_poof.xml" - The entity file to spawn. This indicates that this particle effect itself spawns another entity, likely a more complex particle or effect.
*   **`spawn_direction`**: "0" - The direction in which to spawn the entity (0 usually means no specific direction).
*   **`spawn_radius`**: "0" - The radius around the spawn point for the new entity.

This particle is designed to be a small, quick visual effect, likely used for minor impacts or dissipations.