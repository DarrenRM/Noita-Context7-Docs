---
title: Water Explosion Essence
category: guides
---

<Entity>
	<InheritTransformComponent>
    </InheritTransformComponent>
	
	<MagicConvertMaterialComponent
		from_any_material="1"
        to_material="lava"
        steps_per_frame="5"
        loop="0"
		is_circle="1"
        radius="20" >
    </MagicConvertMaterialComponent>
	
	<LifetimeComponent
		lifetime="4"
	>
	</LifetimeComponent>
  
</Entity>
```

---
title: Water Explosion Essence
category: entities
---

# Water Explosion Essence

This entity defines a special "essence" that, when triggered, converts nearby water into lava.

## Key Components

### MagicConvertMaterialComponent

This is the core component responsible for the material transformation.

*   **`from_any_material`**: Set to `1`, meaning it can convert any material it comes into contact with.
*   **`to_material`**: Specifies the target material, which is `lava` in this case.
*   **`steps_per_frame`**: Controls how many conversion steps occur each frame. A value of `5` indicates a relatively rapid conversion.
*   **`loop`**: Set to `0`, meaning the conversion effect happens once and then stops.
*   **`is_circle`**: Set to `1`, indicating the conversion area is circular.
*   **`radius`**: Defines the size of the circular conversion area, set to `20` units.

### LifetimeComponent

This component determines how long the essence remains active before disappearing.

*   **`lifetime`**: Set to `4` seconds, meaning the conversion effect will persist for this duration.

### InheritTransformComponent

This component is present but empty, suggesting it might be a placeholder or intended for future use in inheriting positional or rotational data. In this specific configuration, it has no functional impact.