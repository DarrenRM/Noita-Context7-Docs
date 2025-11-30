---
title: Drunk Effect Entity
category: guides
---

<Entity>
	
	<InheritTransformComponent>
    </InheritTransformComponent>	
    
    <GameEffectComponent 
        effect="DRUNK"
        frames="3600"
    >
	</GameEffectComponent >

</Entity>
```

---
title: Drunk Effect Entity
category: entities
---

# Drunk Effect Entity

This entity defines the "Drunk" status effect in Noita.

## Key Components

### `GameEffectComponent`

This component manages the application and duration of game effects.

*   **`effect`**: Specifies the type of effect. In this case, it's `"DRUNK"`.
*   **`frames`**: The duration of the effect in game frames. `3600` frames is equivalent to 60 seconds (since 60 frames per second).

### `InheritTransformComponent`

This component is present but empty, indicating that the entity does not inherit any specific transform properties from its parent.