---
title: Moon Effect Test Entity
category: guides
---

<Entity>
    <MagicConvertMaterialComponent
      kill_when_finished="0"
      from_any_material="1"
      steps_per_frame="3"
      to_material="magic_liquid_hp_regeneration"
      clean_stains="0"
      is_circle="1"
      radius="300" 
	  >
    </MagicConvertMaterialComponent>
	
	<LifetimeComponent
		lifetime="160"
		>
	</LifetimeComponent>
</Entity>
```

---
title: Moon Effect Test Entity
category: entities
---

# Moon Effect Test Entity

This entity demonstrates a magical material conversion effect, likely intended for testing or as a component in other entities.

## Key Components

### MagicConvertMaterialComponent

This component handles the conversion of existing materials into a new one.

*   **`from_any_material`**: `1` - Indicates that this component can convert any material it encounters.
*   **`to_material`**: `magic_liquid_hp_regeneration` - Specifies the target material to convert into. In this case, it's a liquid that regenerates HP.
*   **`radius`**: `300` - Defines the area of effect for the material conversion.
*   **`steps_per_frame`**: `3` - Controls how many conversion steps are processed per game frame, affecting the speed of the conversion.
*   **`kill_when_finished`**: `0` - The entity will not be destroyed once the conversion is complete.
*   **`clean_stains`**: `0` - Stains are not cleaned by this effect.
*   **`is_circle`**: `1` - The area of effect is circular.

### LifetimeComponent

This component dictates how long the entity exists.

*   **`lifetime`**: `160` - The entity will persist for 160 game frames.