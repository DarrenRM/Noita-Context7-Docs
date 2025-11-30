---
title: Verlet Vine Long Pixelscene
category: entities
---

# Verlet Vine Long Pixelscene

This entity defines a long, pixelated vine using the Verlet physics system. It's composed of multiple segments and simulates environmental effects like wind and gravity.

## VerletPhysicsComponent

This component governs the physics simulation of the vine.

### Key Attributes:

*   **num_points**: The number of points (segments) that make up the Verlet chain. A higher number results in a more detailed and flexible vine.
    *   Value: `21`
*   **stiffness**: Controls how rigid the vine is. Higher values mean less bending.
    *   Value: `1.0`
*   **velocity_dampening**: Reduces the velocity of the vine's points over time, helping it settle.
    *   Value: `0.9`
*   **resting_distance**: The ideal distance between adjacent points in the chain.
    *   Value: `4`
*   **pixelate_sprite_transforms**: Enables pixelation effects on the vine's sprite as it deforms.
    *   Value: `1` (Enabled)
*   **follow_entity_transform**: If enabled, the entire vine chain would follow the transform of a parent entity.
    *   Value: `0` (Disabled)
*   **simulate_wind**: Enables the simulation of wind forces acting on the vine.
    *   Value: `1` (Enabled)
*   **wind_change_speed**: Controls how quickly the wind's direction and strength change.
    *   Value: `0.25`
*   **simulate_gravity**: Enables the simulation of gravity acting on the vine.
    *   Value: `1` (Enabled)

## Base Components

The vine is constructed from multiple smaller vine segments. The `Base` component references these individual parts.

### Vine Segments:

The following XML files define the visual and physical properties of each vine segment. They are chained together to form the complete vine.

*   `data/entities/verlet_chains/vines/vine_parts/vine_verlet_a_1.xml`
*   `data/entities/verlet_chains/vines/vine_parts/vine_verlet_a_2.xml`
*   `data/entities/verlet_chains/vines/vine_parts/vine_verlet_a_3.xml`
*   `data/entities/verlet_chains/vines/vine_parts/vine_verlet_a_4.xml`
*   `data/entities/verlet_chains/vines/vine_parts/vine_verlet_a_5.xml`
*   `data/entities/verlet_chains/vines/vine_parts/vine_verlet_a_6.xml`
*   `data/entities/verlet_chains/vines/vine_parts/vine_verlet_a_7.xml`
*   `data/entities/verlet_chains/vines/vine_parts/vine_verlet_a_8.xml`

*(Note: The list of `Base` files indicates repetition, suggesting a pattern or loop in the vine's construction.)*

## AudioComponent

This component handles audio events associated with the vine.

### Key Attributes:

*   **file**: The audio bank containing the sound events.
    *   Value: `data/audio/Desktop/materials.bank`
*   **event_root**: The root path for collision sound events related to this vine.
    *   Value: `collision/vine`

```xml
<Entity >
   
    <VerletPhysicsComponent
    	num_points="21"
    	stiffness="1.0"
		velocity_dampening="0.9"
    	resting_distance="4" 
    	pixelate_sprite_transforms="1"
        follow_entity_transform="0"
    	simulate_wind="1"
    	wind_change_speed="0.25"
    	simulate_gravity="1" >
    </VerletPhysicsComponent>

	<Base file="data/entities/verlet_chains/vines/vine_parts/vine_verlet_a_1.xml" />
	<Base file="data/entities/verlet_chains/vines/vine_parts/vine_verlet_a_2.xml" />
	<Base file="data/entities/verlet_chains/vines/vine_parts/vine_verlet_a_3.xml" />
	<Base file="data/entities/verlet_chains/vines/vine_parts/vine_verlet_a_4.xml" />
	<Base file="data/entities/verlet_chains/vines/vine_parts/vine_verlet_a_5.xml" />
	<Base file="data/entities/verlet_chains/vines/vine_parts/vine_verlet_a_6.xml" />
	<Base file="data/entities/verlet_chains/vines/vine_parts/vine_verlet_a_7.xml" />
	<Base file="data/entities/verlet_chains/vines/vine_parts/vine_verlet_a_8.xml" />
	<Base file="data/entities/verlet_chains/vines/vine_parts/vine_verlet_a_1.xml" />
	<Base file="data/entities/verlet_chains/vines/vine_parts/vine_verlet_a_2.xml" />
	<Base file="data/entities/verlet_chains/vines/vine_parts/vine_verlet_a_3.xml" />
	<Base file="data/entities/verlet_chains/vines/vine_parts/vine_verlet_a_4.xml" />
	<Base file="data/entities/verlet_chains/vines/vine_parts/vine_verlet_a_5.xml" />
	<Base file="data/entities/verlet_chains/vines/vine_parts/vine_verlet_a_6.xml" />
	<Base file="data/entities/verlet_chains/vines/vine_parts/vine_verlet_a_7.xml" />
	<Base file="data/entities/verlet_chains/vines/vine_parts/vine_verlet_a_8.xml" />
	<Base file="data/entities/verlet_chains/vines/vine_parts/vine_verlet_a_1.xml" />
	<Base file="data/entities/verlet_chains/vines/vine_parts/vine_verlet_a_2.xml" />
	<Base file="data/entities/verlet_chains/vines/vine_parts/vine_verlet_a_3.xml" />
	<Base file="data/entities/verlet_chains/vines/vine_parts/vine_verlet_a_4.xml" />

	<AudioComponent
		file="data/audio/Desktop/materials.bank"
		event_root="collision/vine" >
	</AudioComponent>
  
</Entity>
```