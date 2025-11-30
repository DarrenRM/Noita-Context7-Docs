---
title: Guts Explosion Trail Particle 02
category: entities/particles
---

# Guts Explosion Trail Particle 02

This entity defines a particle effect used in explosions, specifically a "guts" trail. It inherits its base properties from `explosion_trail_guts_01.xml` and modifies its visual appearance and behavior.

## Key Components

### PhysicsImageShapeComponent

This component defines the visual representation and physical properties of the particle.

*   **`image_file`**: `data/particles/guts_02.png` - Specifies the texture used for this particle.
*   **`material`**: `meat` - Assigns a material type, likely influencing its interaction with other game elements.

### LuaComponent

This component adds custom behavior to the particle using Lua scripting.

*   **`execute_every_n_frame`**: `5` - This setting causes the Lua script associated with this component to execute only once every 5 frames. This is likely used to stagger the initialization or behavior of multiple particles, preventing them from sticking together too closely.

## Inheritance

This entity inherits from:

*   **`data/entities/particles/particle_explosion/explosion_trail_guts_01.xml`**: This indicates that `explosion_trail_guts_02.xml` builds upon the foundational properties of `explosion_trail_guts_01.xml`, likely sharing common explosion trail behaviors and particle settings.

```xml
<Entity>
	<Base file="data/entities/particles/particle_explosion/explosion_trail_guts_01.xml">

		<PhysicsImageShapeComponent
			image_file="data/particles/guts_02.png"
			material="meat"
			>
		</PhysicsImageShapeComponent>

		<!-- staggered init so that guts stick less together -->
		<LuaComponent
			execute_every_n_frame="5"
			>
		</LuaComponent>
	</Base>
</Entity>
```