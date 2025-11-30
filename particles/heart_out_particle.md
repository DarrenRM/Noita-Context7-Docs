---
title: Heart Out Particle
category: guides
---

<Entity>
  
	<SpriteComponent 
		_enabled="1" 
		alpha="1" 
		image_file="data/particles/heart_out.xml" 
		next_rect_animation="explosion" 
		offset_x="0" 
		offset_y="0" 
		rect_animation="" 
		update_transform_rotation="0"
		>
	</SpriteComponent>
	
	<LifetimeComponent 
		lifetime="20"
		>
	</LifetimeComponent>
  
</Entity>
```

---
title: Heart Out Particle
category: entities/particles
---

# Heart Out Particle

This document describes the `heart_out.xml` entity, which defines a particle effect in Noita.

## Entity Definition

The core of this particle is an `<Entity>` tag.

### Key Components

*   **`<SpriteComponent>`**: Defines the visual appearance and animation of the particle.
    *   `image_file`: Specifies the texture file used for the sprite. In this case, it points to `data/particles/heart_out.xml` itself, suggesting a self-referential or placeholder texture.
    *   `next_rect_animation`: Sets the name of the next animation state to transition to. Here, it's set to "explosion".
    *   `alpha`: Controls the transparency of the sprite (1 is fully opaque).
    *   `offset_x`, `offset_y`: Adjusts the sprite's position relative to its entity's origin.
    *   `rect_animation`: Defines the current rectangle animation. It's empty here, implying it might be controlled by `next_rect_animation`.
    *   `update_transform_rotation`: A boolean indicating whether the sprite's rotation should update with the entity's transform. Set to "0" (false).

*   **`<LifetimeComponent>`**: Manages how long the particle exists.
    *   `lifetime`: The duration in seconds the particle will remain active. Set to "20".

This particle appears to be a simple visual effect, likely triggered by an event, that displays a sprite for a set duration and then transitions to an "explosion" animation. The `image_file` pointing to itself is unusual and might indicate a default or placeholder texture that is intended to be overridden by game logic or other components not present in this snippet.