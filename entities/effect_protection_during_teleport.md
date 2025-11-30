---
title: Effect Protection During Teleport
category: entities
---

# Effect Protection During Teleport

This entity defines a game effect that grants the player temporary protection while teleporting.

## Entity Structure

The entity is a simple container for a `GameEffectComponent`.

```xml
<Entity>
	
	<InheritTransformComponent>
    </InheritTransformComponent>	
    
    <GameEffectComponent 
        effect="PROTECTION_DURING_TELEPORT"
        frames="7200"
    >
	</GameEffectComponent >

</Entity>
```

## Key Components

### GameEffectComponent

This component is responsible for applying the actual game effect.

| Attribute | Description                                                              |
| :-------- | :----------------------------------------------------------------------- |
| `effect`  | Specifies the type of effect to apply. In this case, it's `PROTECTION_DURING_TELEPORT`. |
| `frames`  | The duration of the effect in game frames. `7200` frames is equivalent to 2 minutes (7200 / 60 frames per second). |