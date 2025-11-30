---
title: Liquid to Explosion Conversion
category: entities
---

# Liquid to Explosion Conversion

This entity defines a mechanism for converting specific liquids into an explosion. It's a simple yet effective way to create dynamic environmental reactions in Noita.

## MagicConvertMaterialComponent

This component is the core of the entity's functionality, handling the conversion process.

### Key Attributes:

*   **`from_material_tag`**: Specifies the tag of the liquid material that will be converted. In this case, `[liquid_common]` targets a broad range of common liquid types.
*   **`to_material`**: Defines the material that the liquid will be converted into. Here, it's set to `gunpowder_unstable_big`, which is known to cause a significant explosion.
*   **`radius`**: Determines the area of effect for the conversion. A radius of `48` means the conversion will spread outwards from the point of contact.
*   **`steps_per_frame`**: Controls the speed of the conversion process. A higher value means faster conversion.
*   **`loop`**: When set to `1`, the conversion will continuously occur as long as the conditions are met.
*   **`kill_when_finished`**: Set to `0`, indicating that the conversion process does not terminate the entity once completed.
*   **`clean_stains`**: Set to `0`, meaning that any stains left by the original liquid will not be cleaned up after conversion.
*   **`is_circle`**: Set to `1`, ensuring the conversion radius is circular.

```xml
<Entity >
	<MagicConvertMaterialComponent
      kill_when_finished="0"
	  from_material_tag="[liquid_common]"
      steps_per_frame="48"
      to_material="gunpowder_unstable_big"
      clean_stains="0"
      is_circle="1"
      radius="48" 
	  loop="1"
	  >
    </MagicConvertMaterialComponent>
</Entity>
```