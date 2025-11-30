---
title: Boss Centipede Body Chunks
category: entities
---

# Boss Centipede Body Chunks

This entity defines the individual body segments of the Boss Centipede. Each segment is a distinct physics object with its own visual representation and material properties.

## Key Components

### PhysicsBodyComponent
This component defines the physical properties of each body chunk.

| Attribute             | Description                                                                 |
| :-------------------- | :-------------------------------------------------------------------------- |
| `uid`                 | Unique identifier for the physics body.                                     |
| `allow_sleep`         | If `1`, the body can go to sleep when not in motion to save performance.    |
| `angular_damping`     | Resistance to rotational movement.                                          |
| `fixed_rotation`      | If `1`, the body's rotation is locked.                                      |
| `is_bullet`           | If `1`, the body behaves like a bullet (e.g., collides with everything).    |
| `linear_damping`      | Resistance to linear movement.                                              |
| `update_entity_transform` | If `1`, the entity's transform is updated based on physics.                 |
| `on_death_leave_physics_body` | If `1`, the physics body remains after the entity is destroyed.             |

### PhysicsImageShapeComponent
This component defines the visual shape and material of the body chunk, linked to a specific `PhysicsBodyComponent` via `body_id`.

| Attribute      | Description                                                                 |
| :------------- | :-------------------------------------------------------------------------- |
| `body_id`      | The `uid` of the `PhysicsBodyComponent` this shape is attached to.          |
| `centered`     | If `0`, the image's origin is at its top-left corner.                       |
| `offset_x`     | Horizontal offset of the image from the physics body's origin.              |
| `offset_y`     | Vertical offset of the image from the physics body's origin.                |
| `image_file`   | Path to the image file used for this body chunk.                            |
| `material`     | The material of the body chunk (e.g., `meat_slime_green`).                  |

### SpriteParticleEmitterComponent
This component defines a particle effect that is emitted when the entity is destroyed.

| Attribute                  | Description                                                                 |
| :------------------------- | :-------------------------------------------------------------------------- |
| `sprite_file`              | Path to the particle sprite definition.                                     |
| `emission_interval_min_frames` | Minimum frames between particle emissions. Set very high to emit only on death. |
| `emission_interval_max_frames` | Maximum frames between particle emissions. Set very high to emit only on death. |
| `count_min`                | Minimum number of particles to emit.                                        |
| `count_max`                | Maximum number of particles to emit.                                        |
| `sprite_random_rotation`   | If `1`, particles will have random rotation.                                |
| `randomize_position.min_y` | Minimum Y-axis randomization for particle spawn position.                   |
| `randomize_position.max_y` | Maximum Y-axis randomization for particle spawn position.                   |
| `randomize_position.min_x` | Minimum X-axis randomization for particle spawn position.                   |
| `randomize_position.max_x` | Maximum X-axis randomization for particle spawn position.                   |

## Example Body Chunk Definition

Each body chunk is defined by a pair of `PhysicsBodyComponent` and `PhysicsImageShapeComponent`.

```xml
<Entity tags="hittable" >

	<PhysicsBodyComponent 
		uid="1" 
		allow_sleep="1" 
		angular_damping="0.1" 
		fixed_rotation="0" 
		is_bullet="0" 
		linear_damping="0"
		update_entity_transform="1"
		on_death_leave_physics_body="1"
		>
	</PhysicsBodyComponent>
	<PhysicsImageShapeComponent 
		body_id="1"
		centered="0"
		offset_x="40"
		offset_y="40"
		image_file="data/entities/animals/boss_centipede/body_chunk_01.png"
		material="meat_slime_green" >
	</PhysicsImageShapeComponent>

	<!-- ... other body chunks ... -->

	<SpriteParticleEmitterComponent
		sprite_file="data/particles/explosion_032_slime.xml"
		emission_interval_min_frames="9999999999"
		emission_interval_max_frames="9999999999"
		count_min="20"
		count_max="20"
		sprite_random_rotation="1"
		randomize_position.min_y="0" 
		randomize_position.max_y="50"
		randomize_position.min_x="-25"  
		randomize_position.max_x="25"
		>
	</SpriteParticleEmitterComponent>

</Entity>
```