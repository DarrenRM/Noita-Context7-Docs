---
title: Blue Verlet Vine
category: entities
---

# Blue Verlet Vine

This entity defines a blue vine using the Verlet physics system. It's composed of multiple segments and interacts with the environment through physics and sound.

## VerletPhysicsComponent

This component governs the physics simulation of the vine.

### Key Attributes:

*   `num_points`: The number of points (segments) that make up the Verlet chain. Higher values result in a more detailed and flexible vine.
*   `stiffness`: Controls how rigid the vine is. A value of `1.0` indicates a relatively stiff vine.
*   `velocity_dampening`: Reduces the velocity of the vine's points over time, helping it settle. `0.9` means 90% of velocity is retained each step.
*   `resting_distance`: The ideal distance between adjacent points in the chain when no forces are applied.
*   `simulate_wind`: Enables the simulation of wind forces acting on the vine.
*   `simulate_gravity`: Enables the simulation of gravity acting on the vine.

```xml
<VerletPhysicsComponent
	num_points="15"
	stiffness="1.0"
	velocity_dampening="0.9"
	resting_distance="4"
	simulate_wind="1"
	simulate_gravity="1" >
</VerletPhysicsComponent>
```

## Base Components

The vine is constructed from multiple `Base` entities, each representing a visual segment of the vine. These are loaded sequentially to form the complete chain.

### Included Segments:

*   `data/entities/verlet_chains/vines/vine_parts_blue/vine_verlet_b_1.xml`
*   `data/entities/verlet_chains/vines/vine_parts_blue/vine_verlet_b_2.xml`
*   `data/entities/verlet_chains/vines/vine_parts_blue/vine_verlet_b_3.xml`
*   `data/entities/verlet_chains/vines/vine_parts_blue/vine_verlet_b_4.xml`
*   `data/entities/verlet_chains/vines/vine_parts_blue/vine_verlet_b_5.xml`
*   `data/entities/verlet_chains/vines/vine_parts_blue/vine_verlet_b_6.xml`
*   `data/entities/verlet_chains/vines/vine_parts_blue/vine_verlet_b_7.xml`
*   `data/entities/verlet_chains/vines/vine_parts_blue/vine_verlet_b_8.xml`

*(Note: Some segments are listed multiple times, which may indicate redundancy or specific layering in the original asset.)*

```xml
<Base file="data/entities/verlet_chains/vines/vine_parts_blue/vine_verlet_b_1.xml" />
<!-- ... other vine_verlet_b_X.xml files ... -->
```

## MoveToSurfaceOnCreateComponent

This component ensures that when the vine is created, it attempts to attach itself to the nearest surface.

### Key Attributes:

*   `verlet_min_joint_distance`: The minimum distance between joints for the attachment to be considered valid.
*   `type`: Specifies the type of Verlet rope behavior, in this case, `VERLET_ROPE_TWO_JOINTS`.

```xml
<MoveToSurfaceOnCreateComponent
	verlet_min_joint_distance="28"
	type="VERLET_ROPE_TWO_JOINTS" >
</MoveToSurfaceOnCreateComponent>
```

## AudioComponent

This component handles the sound effects associated with the vine, specifically for collision events.

### Key Attributes:

*   `file`: The audio bank file containing the sound events.
*   `event_root`: The root path for the sound events related to vine collisions.

```xml
<AudioComponent
	file="data/audio/Desktop/materials.bank"
	event_root="collision/vine" >
</AudioComponent>
```