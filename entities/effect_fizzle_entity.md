---
title: Effect Fizzle Entity
category: guides
---

<Entity>
	
	<InheritTransformComponent>
    </InheritTransformComponent>	
    
    <ShotEffectComponent
        extra_modifier="fizzle"
		>
	</ShotEffectComponent>
	
	<LifetimeComponent
		lifetime="3600"
		>
	</LifetimeComponent>

</Entity>
```

---
title: Effect Fizzle Entity
category: entities
---

# Effect Fizzle Entity

This entity defines a "fizzle" effect that can be applied to projectiles or other entities in Noita.

## Key Components and Attributes

### ShotEffectComponent

This component is responsible for applying the visual and functional effect of fizzling.

*   **`extra_modifier`**: Set to `"fizzle"`. This is the core identifier for this specific effect.

### LifetimeComponent

Determines how long the fizzle effect persists.

*   **`lifetime`**: Set to `3600`. This indicates the effect will last for 3600 game frames (approximately 1 minute).

### InheritTransformComponent

This component is present but has no specific attributes defined, suggesting it inherits transform properties from its parent or the environment.