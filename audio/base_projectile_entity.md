---
title: Base Projectile Entity
category: guides
---

<Entity tags="teleportable_NOT,projectile">
	
	<VelocityComponent
		mass="0.05"
		affect_physics_bodies="1" >
	</VelocityComponent>

	<AudioComponent
		file="data/audio/Desktop/projectiles.bank"
		audio_physics_material="projectile"
		event_root="projectiles/hit" >
	</AudioComponent>

</Entity>
```

---
title: Base Projectile Entity
category: entities
---

# Base Projectile Entity

This document describes the fundamental `base_projectile.xml` entity, serving as a template for most projectiles in Noita. It defines core properties related to physics and sound.

## Key Components

### VelocityComponent

This component governs the projectile's physical movement and interaction with the environment.

| Attribute             | Description                                                                 |
| :-------------------- | :-------------------------------------------------------------------------- |
| `mass`                | The mass of the projectile, affecting its inertia and how it interacts with forces. |
| `affect_physics_bodies` | Determines if the projectile's velocity influences other physics objects it collides with. |

### AudioComponent

This component handles the sound effects associated with the projectile, particularly when it impacts something.

| Attribute             | Description                                                                 |
| :-------------------- | :-------------------------------------------------------------------------- |
| `file`                | The path to the audio bank file containing the projectile's sound events.   |
| `audio_physics_material` | Specifies the physics material used for sound generation on impact.         |
| `event_root`          | The base name for sound events related to projectile impacts.               |

## Key Tags

*   `teleportable_NOT`: Indicates that this entity cannot be teleported.
*   `projectile`: Identifies the entity as a projectile.