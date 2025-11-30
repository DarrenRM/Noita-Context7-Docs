---
title: Effect Stains Drop Faster
category: entities
---

# Effect Stains Drop Faster

This entity defines a game effect that causes stains to fall faster.

## Entity Definition

```xml
<Entity>
	<InheritTransformComponent>
    </InheritTransformComponent>	
    
    <GameEffectComponent 
    	effect="STAINS_DROP_FASTER"
    	frames="600"
    >
	</GameEffectComponent >
	
</Entity>
```

## Key Components and Attributes

### GameEffectComponent

This component applies a specific game effect.

*   **`effect`**: Specifies the type of effect. In this case, it's `"STAINS_DROP_FASTER"`.
*   **`frames`**: The duration of the effect in game frames. Here, it's set to `600` frames.