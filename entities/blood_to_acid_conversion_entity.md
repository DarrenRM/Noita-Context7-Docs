---
title: Blood to Acid Conversion Entity
category: entities
---

# Blood to Acid Conversion Entity

This entity defines a magical effect that converts specific types of blood materials into acid. It's designed to be applied to other entities or used as a standalone effect.

## Key Components

### MagicConvertMaterialComponent

This component handles the material conversion process.

| Attribute         | Description                                                                 |
| :---------------- | :-------------------------------------------------------------------------- |
| `from_material`   | The material to be converted (e.g., "blood", "blood_fading").              |
| `to_material`     | The material to convert to (e.g., "acid").                                  |
| `radius`          | The radius of the conversion effect.                                        |
| `steps_per_frame` | Controls the speed and smoothness of the conversion. Higher values mean faster conversion. |
| `loop`            | If `1`, the conversion effect will repeat continuously.                     |
| `kill_when_finished` | If `0`, the component will not be removed after the conversion is complete. |
| `clean_stains`    | If `0`, existing stains of the `from_material` will not be cleaned.         |
| `is_circle`       | If `1`, the conversion effect is applied in a circular area.                |

## Usage

This entity is typically used as a component within other entities that need to create an acid pool or effect from blood. For example, it could be attached to a spell that splashes blood, which then converts to acid.

## Example Configuration

```xml
<Entity >
	<MagicConvertMaterialComponent
      kill_when_finished="0"
      from_material="blood"
      steps_per_frame="48"
      to_material="acid"
      clean_stains="0"
      is_circle="1"
      radius="48"
	  loop="1"
	  >
    </MagicConvertMaterialComponent>

	<MagicConvertMaterialComponent
      kill_when_finished="0"
      from_material="blood_fading"
      steps_per_frame="48"
      to_material="acid"
      clean_stains="0"
      is_circle="1"
      radius="48"
	  loop="1"
	  >
    </MagicConvertMaterialComponent>
</Entity>
```