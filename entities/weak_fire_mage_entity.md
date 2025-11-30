---
title: Weak Fire Mage Entity
category: entities
---

# Weak Fire Mage Entity

This document describes the `firemage_weak.xml` entity, a less powerful variant of the Fire Mage found in Noita. It inherits most of its behavior from the base `firemage.xml` but has reduced health and a distinct sprite.

## Key Attributes

### Base Entity Inheritance

The `firemage_weak.xml` entity primarily inherits from `data/entities/animals/firemage.xml`. This means it shares core AI, movement, and attack logic with its stronger counterpart.

### AnimalAIComponent

*   **`attack_ranged_entity_file`**: Specifies the projectile used for ranged attacks.
    *   Value: `data/entities/projectiles/fireball.xml`

### DamageModelComponent

*   **`hp`**: Defines the health points of the entity.
    *   Value: `3.2` (Significantly lower than a standard Fire Mage)

### SpriteComponent

*   **`image_file`**: Points to the graphical assets for this specific entity.
    *   Value: `data/enemies_gfx/firemage_weak.xml`

## Particle Effects

The weak fire mage utilizes several particle emitters to simulate fiery effects. These are attached to the entity's base and its left hand.

### Base Torch Particle Effects

These emitters are attached to the main body of the fire mage, likely for a general fiery aura.

*   **`ParticleEmitterComponent` (x3)**:
    *   `x_pos_offset_min`: `-2`
    *   `x_pos_offset_max`: `2`

### Left Hand Particle Effects (`hand_l`)

These emitters are attached to the entity's left hand, simulating fire being cast or held.

*   **`ParticleEmitterComponent` (x3)**:
    *   **Emitter 1 & 2**:
        *   `count_min`: `2`
        *   `count_max`: `3`
        *   `x_pos_offset_min`: `-1`
        *   `x_pos_offset_max`: `1`
        *   `y_pos_offset_min`: `-1`
        *   `y_pos_offset_max`: `2`
    *   **Emitter 3**:
        *   `x_pos_offset_min`: `-1`
        *   `x_pos_offset_max`: `1`
        *   `y_pos_offset_min`: `-3`
        *   `y_pos_offset_max`: `2`

### InheritTransformComponent (for `hand_l`)

*   **`parent_hotspot_tag`**: `hand_l` - Links these particle effects to the left hand's transform.
*   **`only_position`**: `1` - Ensures only the position is inherited, not rotation or scale.

```xml
<Entity name="$animal_firemage_weak" tags="firemage" >
	<Base file="data/entities/animals/firemage.xml" >
		<AnimalAIComponent
			attack_ranged_entity_file="data/entities/projectiles/fireball.xml"
			>
		</AnimalAIComponent>
		<DamageModelComponent
			hp="3.2"
			>
		</DamageModelComponent>
		<SpriteComponent 
			image_file="data/enemies_gfx/firemage_weak.xml" 
			>
		</SpriteComponent> 
	</Base>
	<Entity>
		<InheritTransformComponent>
			<Transform 
				position.x="0"
				position.y="-12" 
				>
			</Transform>
		</InheritTransformComponent>
		<Base file="data/entities/base_torch_particle.xml" >
			<ParticleEmitterComponent 
				x_pos_offset_min="-2"
				x_pos_offset_max="2" >
			</ParticleEmitterComponent>
			<ParticleEmitterComponent 
				x_pos_offset_min="-2"
				x_pos_offset_max="2" >
			</ParticleEmitterComponent>
			<ParticleEmitterComponent 
				x_pos_offset_min="-2"
				x_pos_offset_max="2" >
			</ParticleEmitterComponent>
		</Base>
	</Entity>
	<Entity name="hand_l">	
		<Base file="data/entities/base_torch_particle.xml" >
			<ParticleEmitterComponent 
				count_min="2"
				count_max="3"
				x_pos_offset_min="-1"
				x_pos_offset_max="1" 
				y_pos_offset_min="-1"
				y_pos_offset_max="2"
				>
			</ParticleEmitterComponent>
			<ParticleEmitterComponent 
				count_min="2"
				count_max="3"
				x_pos_offset_min="-1"
				x_pos_offset_max="1" 
				y_pos_offset_min="-1"
				y_pos_offset_max="2">
			</ParticleEmitterComponent>
			<ParticleEmitterComponent 
				x_pos_offset_min="-1"
				x_pos_offset_max="1" 
				y_pos_offset_min="-3"
				y_pos_offset_max="2">
			</ParticleEmitterComponent>
		</Base>
		<InheritTransformComponent
			parent_hotspot_tag="hand_l"
			only_position="1" >
		</InheritTransformComponent>
	</Entity>
</Entity>
```