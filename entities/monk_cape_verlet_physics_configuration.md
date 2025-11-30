---
title: Monk Cape Verlet Physics Configuration
category: entities
---

# Monk Cape Verlet Physics Configuration

This document details the configuration for the Monk Cape's verlet physics, enabling its dynamic, cloth-like behavior in Noita.

## Entity Definition

The core of the Monk Cape's physics is defined by the `VerletPhysicsComponent`.

```xml
<Entity >
	
	<InheritTransformComponent>
	</InheritTransformComponent>
   
    <VerletPhysicsComponent
    	stiffness="1.0"
    	num_points="5"
		velocity_dampening="0.8"
    	resting_distance="3.0"
		scale_sprite_x="0"
		pixelate_sprite_transforms="0"
		simulate_gravity="1"
		mass_min="0.1"
		mass_max="0.9"
		animation_amount="4"
		animation_energy="0.4"
		>
    </VerletPhysicsComponent>

	<Base file="data/entities/verlet_chains/monk_cape/parts/cape_verlet_1.xml" />
	<Base file="data/entities/verlet_chains/monk_cape/parts/cape_verlet_2.xml" />
	<Base file="data/entities/verlet_chains/monk_cape/parts/cape_verlet_3.xml" />
	<Base file="data/entities/verlet_chains/monk_cape/parts/cape_verlet_4.xml" />
</Entity>
```

## Key `VerletPhysicsComponent` Attributes

These attributes control the fundamental behavior and appearance of the verlet chain:

| Attribute           | Description