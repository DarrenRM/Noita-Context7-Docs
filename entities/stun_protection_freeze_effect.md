---
title: Stun Protection (Freeze) Effect
category: entities
---

# Stun Protection (Freeze) Effect

This entity defines a game effect that grants temporary protection against being frozen.

## Entity Definition

```xml
<Entity tags="effect_protection" >
	
	<InheritTransformComponent>
    </InheritTransformComponent>	
    
    <GameEffectComponent
		_tags="effect_protection"
        effect="STUN_PROTECTION_FREEZE"
        frames="7200"
    >
	</GameEffectComponent >

</Entity>
```

## Key Components and Attributes

### `GameEffectComponent`

This component is responsible for defining the actual game effect.

*   **`effect`**: Specifies the type of effect. In this case, it's `STUN_PROTECTION_FREEZE`, indicating protection against freezing.
*   **`frames`**: Determines the duration of the effect in game frames. `7200` frames is equivalent to 2 minutes (7200 frames / 60 frames per second = 120 seconds).

### `InheritTransformComponent`

This component is present but has no specific attributes defined, suggesting it inherits default transform properties.

## Usage

This entity is likely used to apply a temporary buff to a character or object, preventing them from being frozen by other game mechanics.