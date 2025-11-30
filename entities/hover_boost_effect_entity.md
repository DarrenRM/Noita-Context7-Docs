---
title: Hover Boost Effect Entity
category: guides
---

<Entity>
	<InheritTransformComponent>
    </InheritTransformComponent>	
    
    <GameEffectComponent 
    	effect="HOVER_BOOST"
    	frames="600"
    >
	</GameEffectComponent >
	
</Entity>
```

---
title: Hover Boost Effect Entity
category: entities
---

# Hover Boost Effect Entity

This entity defines the behavior and properties of the "Hover Boost" game effect in Noita.

## Key Components

### `GameEffectComponent`

This component is responsible for applying the game effect.

*   **`effect`**: Specifies the type of effect. In this case, it's `"HOVER_BOOST"`.
*   **`frames`**: The duration of the effect in frames. Here, it's set to `600` frames (approximately 10 seconds).

### `InheritTransformComponent`

This component indicates that the entity inherits its transform properties (position, rotation, scale) from its parent. This is a common component for effects that are attached to other entities.