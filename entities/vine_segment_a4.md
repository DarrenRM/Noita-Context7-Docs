---
title: Vine Segment A4
category: guides
---

<Entity
 name="vine_a_4"
 tags="small,plant,vine,breakable"
 >

 <!-- Sprite for the vine segment -->
 <Sprite
  filename="data/entities/verlet_chains/vines/vine_parts/vine_a.png"
  offset_x="0"
  offset_y="0"
  default_animation="stand" >
  <!-- Animation details for the vine segment -->
  <RectAnimation
   name="stand"
   pos_x="12"
   pos_y="0"
   frame_count="1"
   frame_width="4"
   frame_height="3"
   frame_wait="1"
   frames_per_row="8"
   loop="1"
   >
  </RectAnimation>
 </Sprite>

 <!-- Physics properties for the vine segment -->
 <Physics
  is_physical="1"
  is_kinematic="0"
  gravity_scale="0.1"
  friction="0.5"
  restitution="0.1"
  air_friction="0.0"
  mass="0.1"
  >
 </Physics>

 <!-- Collision properties for the vine segment -->
 <Collision
  width="4"
  height="3"
  offset_x="0"
  offset_y="0"
  >
 </Collision>

 <!-- Damage properties for the vine segment -->
 <Damage
  is_damageable="1"
  hp="1"
  >
 </Damage>

 <!-- Material properties for the vine segment -->
 <Material
  is_material="1"
  material_type="organic"
  >
 </Material>

 <!-- Particle emitter for when the vine segment is destroyed -->
 <ParticleEmitter
  particle_object="data/particles/dust.xml"
  randomize_position="1"
  randomize_rotation="1"
  count_min="1"
  count_max="3"
  >
 </ParticleEmitter>

 <!-- Sound effect for when the vine segment is destroyed -->
 <Sound
  file="data/sounds/destroy_small.ogg"
  play_on_death="1"
  >
 </Sound>

 <!-- This entity is part of a verlet chain, defining its connection to other segments -->
 <VerletChain2D
  chain_length="1"
  segment_length="4"
  stiffness="0.5"
  damping="0.1"
  >
 </VerletChain2D>

</Entity>
```

---
title: Vine Segment A4
category: entities
---

# Vine Segment A4

This document details the `vine_a_4` entity, representing a segment of a vine in Noita. It is designed to be part of a `VerletChain2D` for flexible, physics-driven growth and interaction.

## Key Attributes

### Sprite

The visual representation of the vine segment.

| Attribute      | Value                                             | Description                                                              |
|----------------|---------------------------------------------------|--------------------------------------------------------------------------|
| `filename`     | `data/entities/verlet_chains/vines/vine_parts/vine_a.png` | Path to the sprite texture.                                              |
| `offset_x`     | `0`                                               | Horizontal offset of the sprite.                                         |
| `offset_y`     | `0`                                               | Vertical offset of the sprite.                                           |
| `default_animation` | `stand`                                           | The default animation to play.                                           |

#### RectAnimation (stand)

Details of the sprite's animation.

| Attribute       | Value | Description                                      |
|-----------------|-------|--------------------------------------------------|
| `name`          | `stand` | Name of the animation.                           |
| `pos_x`         | `12`  | X-coordinate of the sprite frame within the sheet. |
| `pos_y`         | `0`   | Y-coordinate of the sprite frame within the sheet. |
| `frame_count`   | `1`   | Number of frames in the animation.               |
| `frame_width`   | `4`   | Width of a single animation frame.               |
| `frame_height`  | `3`   | Height of a single animation frame.              |
| `frame_wait`    | `1`   | Time in frames to wait before advancing.         |
| `frames_per_row`| `8`   | Number of frames per row in the sprite sheet.    |
| `loop`          | `1`   | Whether the animation should loop (1 for yes).   |

### Physics

Defines the physical properties of the vine segment.

| Attribute      | Value | Description                                      |
|----------------|-------|--------------------------------------------------|
| `is_physical`  | `1`   | Whether the entity is subject to physics.        |
| `is_kinematic` | `0`   | Whether the entity's movement is controlled by physics. |
| `gravity_scale`| `0.1` | How strongly gravity affects this entity.        |
| `mass`         | `0.1` | The mass of the vine segment.                    |

### Collision

Defines the collision boundaries of the vine segment.

| Attribute | Value | Description                               |
|-----------|-------|-------------------------------------------|
| `width`   | `4`   | Width of the collision box.               |
| `height`  | `3`   | Height of the collision box.              |
| `offset_x`| `0`   | Horizontal offset of the collision box.   |
| `offset_y`| `0`   | Vertical offset of the collision box.     |

### Damage

Defines how the vine segment can be damaged.

| Attribute     | Value | Description                               |
|---------------|-------|-------------------------------------------|
| `is_damageable`| `1`   | Whether the entity can take damage.       |
| `hp`          | `1`   | Hit points of the vine segment.           |

### Material

Defines the material properties of the vine segment.

| Attribute     | Value   | Description                               |
|---------------|---------|-------------------------------------------|
| `is_material` | `1`     | Whether this entity has material properties. |
| `material_type`| `organic`| The type of material.                     |

### ParticleEmitter

Specifies particles to be emitted upon destruction.

| Attribute           | Value                               | Description                                      |
|---------------------|-------------------------------------|--------------------------------------------------|
| `particle_object`   | `data/particles/dust.xml`           | Path to the particle effect to emit.             |
| `randomize_position`| `1`                                 | Whether to randomize particle emission position. |
| `randomize_rotation`| `1`                                 | Whether to randomize particle emission rotation. |
| `count_min`         | `1`                                 | Minimum number of particles to emit.             |
| `count_max`         | `3`                                 | Maximum number of particles to emit.             |

### Sound

Specifies sound effects to be played.

| Attribute      | Value                         | Description                               |
|----------------|-------------------------------|-------------------------------------------|
| `file`         | `data/sounds/destroy_small.ogg` | Path to the sound file to play.           |
| `play_on_death`| `1`                           | Whether to play the sound when the entity dies. |

### VerletChain2D

Crucial for defining the vine's behavior as part of a connected chain.

| Attribute     | Value | Description                                      |
|---------------|-------|--------------------------------------------------|
| `chain_length`| `1`   | The number of segments in this chain (this segment is 1). |
| `segment_length`| `4`   | The length of each segment in the chain.         |
| `stiffness`   | `0.5` | How rigid the chain is.                          |
| `damping`     | `0.1` | How quickly oscillations in the chain dissipate. |

## Summary

The `vine_a_4` entity is a fundamental building block for creating dynamic vine structures in Noita. Its `VerletChain2D` component allows for realistic physics-based movement and interaction, while its sprite, physics, collision, and damage properties define its visual and interactive behavior. When destroyed, it emits dust particles and plays a small destruction sound.