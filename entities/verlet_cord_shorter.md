---
title: Verlet Cord (Shorter)
category: entities
---

# Verlet Cord (Shorter)

This entity defines a shorter, more rigid verlet cord. It's composed of multiple segments, each with its own physics properties, and is designed to attach to surfaces.

## VerletPhysicsComponent

This component governs the physics simulation of the verlet cord.

### Key Attributes:

*   **num\_points**: The number of points (segments) in the verlet chain. A lower number results in a shorter cord.
*   **stiffness**: Controls how much the cord resists stretching. Higher values mean a stiffer cord.
*   **velocity\_dampening**: Reduces the velocity of the points each frame, making the simulation more stable and less "bouncy".
*   **resting\_distance**: The ideal distance between adjacent points when no forces are applied.
*   **simulate\_wind**: Enables or disables wind simulation for the cord.
*   **simulate\_gravity**: Enables or disables gravity simulation for the cord.

```xml
<VerletPhysicsComponent
	num_points="6"
	stiffness="1.0"
	velocity_dampening="0.9"
	resting_distance="4"
	pixelate_sprite_transforms="1"
	follow_entity_transform="0"
	simulate_wind="1"
	wind_change_speed="0.25"
	simulate_gravity="1" >
</VerletPhysicsComponent>
```

## Base Components

The cord is constructed from several base entity files, defining the visual appearance and individual segments of the cord.

### Key Elements:

*   **Base file**: Each `<Base>` tag points to an XML file that defines a part of the cord. These files likely contain sprite information and potentially other physics-related configurations for each segment.

```xml
<Base file="data/entities/verlet_chains/cords/cord_parts/cord_verlet_a_1.xml" />
<Base file="data/entities/verlet_chains/cords/cord_parts/cord_verlet_a_2.xml" />
<Base file="data/entities/verlet_chains/cords/cord_parts/cord_verlet_a_6.xml" />
<Base file="data/entities/verlet_chains/cords/cord_parts/cord_verlet_a_7.xml" />
<Base file="data/entities/verlet_chains/cords/cord_parts/cord_verlet_a_8.xml" />
```

## MoveToSurfaceOnCreateComponent

This component ensures that when the cord is created, it attempts to attach itself to the nearest surface.

### Key Attributes:

*   **lookup\_radius**: The radius within which the component searches for a surface to attach to.
*   **verlet\_min\_joint\_distance**: The minimum distance required between verlet joints for a successful attachment.
*   **type**: Specifies the type of attachment. `VERLET_ROPE_ONE_JOINT` indicates a single point of attachment for the rope.

```xml
<MoveToSurfaceOnCreateComponent
	lookup_radius="20"
	verlet_min_joint_distance="10"
	type="VERLET_ROPE_ONE_JOINT" >
</MoveToSurfaceOnCreateComponent>
```