---
title: Movement Faster 2x Effect
category: entities
---

# Movement Faster 2x Effect

This entity defines a game effect that doubles the player's movement speed for a limited duration.

## Entity Definition

The core of this entity is the `GameEffectComponent`, which specifies the type of effect and its duration.

### Key Components

*   **`GameEffectComponent`**:
    *   `effect`: `MOVEMENT_FASTER_2X` - This is the identifier for the effect that increases movement speed by 2 times.
    *   `frames`: `600` - The duration of the effect in game frames. At 60 frames per second, this equates to 10 seconds.

### XML Structure

```xml
<Entity>
	<InheritTransformComponent>
    </InheritTransformComponent>	
    
    <GameEffectComponent 
    	effect="MOVEMENT_FASTER_2X"
    	frames="600"
    >
	</GameEffectComponent >
	
</Entity>
```