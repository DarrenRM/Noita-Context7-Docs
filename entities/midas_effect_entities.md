---
title: Midas Effect Entities
category: entities
---

# Midas Effect Entities

This document describes entities related to the "Midas effect" in Noita, specifically focusing on how certain materials or entities are converted into gold.

## MagicConvertMaterialComponent

This component is responsible for the magical conversion of materials and entities into gold.

### Key Attributes:

*   **`kill_when_finished`**: If set to `1`, the entity with this component will be destroyed once the conversion process is complete.
*   **`convert_entities`**: If set to `1`, this component will also attempt to convert other entities within its radius into gold.
*   **`steps_per_frame`**: Controls the speed of the conversion process. Higher values mean faster conversion.
*   **`to_material`**: Specifies the target material to convert into. In this case, it's set to `"gold_b2"`.
*   **`clean_stains`**: If set to `0`, existing stains will not be removed during the conversion.
*   **`is_circle`**: If set to `1`, the conversion radius is circular.
*   **`radius`**: Defines the area of effect for the material and entity conversion.

```xml
<Entity>
	<MagicConvertMaterialComponent
      kill_when_finished="1"
      convert_entities="1"
      steps_per_frame="1"
      to_material="gold_b2"
      clean_stains="0"
      is_circle="1"
      radius="320" >
    </MagicConvertMaterialComponent>
</Entity>
```