---
title: Global Gore Effect
category: entities
---

# Global Gore Effect

This entity defines a global game effect that influences gore behavior.

## Key Components

### GameEffectComponent

This component is responsible for applying the specified game effect.

*   **`effect`**: `GLOBAL_GORE` - This is the core identifier for the gore effect.
*   **`frames`**: `600` - The duration in frames for which this effect will be active.

## XML Structure

```xml
<Entity>
	<InheritTransformComponent>
    </InheritTransformComponent>	
    
    <GameEffectComponent 
    	effect="GLOBAL_GORE"
    	frames="600"
    >
	</GameEffectComponent >
	
</Entity>
```