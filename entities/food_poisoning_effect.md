---
title: Food Poisoning Effect
category: entities
---

# Food Poisoning Effect

This entity defines the game effect of food poisoning in Noita.

## GameEffectComponent

This component governs the behavior and duration of the food poisoning effect.

### Key Attributes:

*   **`effect`**: Specifies the type of game effect. In this case, it's set to `FOOD_POISONING`.
*   **`frames`**: Determines the duration of the effect in game frames. A value of `600` frames translates to 10 seconds (60 frames per second).

## Entity Structure

The entity is a simple container for the `GameEffectComponent`, indicating that it primarily serves to apply this specific game effect.

```xml
<Entity>
	<InheritTransformComponent>
    </InheritTransformComponent>	
    
    <GameEffectComponent 
    	effect="FOOD_POISONING"
    	frames="600"
    >
	</GameEffectComponent >
	
</Entity>
```