---
title: Boss Centipede Clear Materials Entity
category: entities
---

# Boss Centipede Clear Materials Entity

This entity defines a clearing effect used by the Boss Centipede. It utilizes `MagicConvertMaterialComponent` to transform various hazardous materials into air within a specified radius.

## Key Components

### MagicConvertMaterialComponent

This component is responsible for the material conversion effect.

*   **`from_material_array`**: A comma-separated list of materials to be converted.
*   **`to_material_array`**: A comma-separated list of materials to convert to. In this case, it's consistently "air".
*   **`kill_when_finished`**: If set to "1", the entity is removed once the conversion is complete.
*   **`steps_per_frame`**: Controls the speed of the conversion process. Higher values mean faster conversion.
*   **`clean_stains`**: If set to "0", existing stains of the converted materials are not removed.
*   **`is_circle`**: If set to "1", the conversion area is circular.
*   **`radius`**: The radius of the circular conversion area.

#### Active Conversion (First Component)

This is the primary active component, converting multiple hazardous liquids into air.

```xml
<MagicConvertMaterialComponent
    from_material_array="lava,radioactive_liquid,acid,poison"
    to_material_array="air,air,air,air"
    kill_when_finished="1"
    steps_per_frame="10"
    clean_stains="0"
    is_circle="1"
    radius="256"
>
</MagicConvertMaterialComponent>
```

#### Disabled Conversions (Examples)

The following `MagicConvertMaterialComponent` instances are present but disabled (`_enabled="0"`). They demonstrate the potential to convert other materials like soil, blood, and static rocks into air, but are not currently active in this entity.

```xml
<MagicConvertMaterialComponent
    kill_when_finished="1"
    from_material="soil"
    steps_per_frame="10"
    to_material="air"
    clean_stains="0"
    is_circle="1"
    radius="256"
    _enabled="0"
>
</MagicConvertMaterialComponent>

<MagicConvertMaterialComponent
    kill_when_finished="1"
    from_material="blood"
    steps_per_frame="10"
    to_material="air"
    clean_stains="0"
    is_circle="1"
    radius="256"
    _enabled="0"
>
</MagicConvertMaterialComponent>

<MagicConvertMaterialComponent
    kill_when_finished="1"
    from_material="lavarock_static"
    steps_per_frame="10"
    to_material="air"
    clean_stains="0"
    is_circle="1"
    radius="256"
    _enabled="0"
>
</MagicConvertMaterialComponent>

<MagicConvertMaterialComponent
    kill_when_finished="1"
    from_material="rock_static_radioactive"
    steps_per_frame="10"
    to_material="air"
    clean_stains="0"
    is_circle="1"
    radius="256"
    _enabled="0"
>
</MagicConvertMaterialComponent>

<MagicConvertMaterialComponent
    kill_when_finished="1"
    from_material="rock_static_poison"
    steps_per_frame="10"
    to_material="air"
    clean_stains="0"
    is_circle="1"
    radius="256"
    _enabled="0"
>
</MagicConvertMaterialComponent>
```

### LoadEntitiesComponent

This component loads another entity file, likely for visual representation or additional effects associated with the clearing.

*   **`entity_file`**: The path to the entity file to be loaded.

```xml
<LoadEntitiesComponent
    count.min="1"
    count.max="1"
    kill_entity="0"
    entity_file="data/entities/animals/boss_centipede/clear_materials_image.xml" >
</LoadEntitiesComponent>
```

### LifetimeComponent

Determines how long the entity persists before being removed.

*   **`lifetime`**: The duration in frames the entity will exist.

```xml
<LifetimeComponent
    lifetime="80"
>
</LifetimeComponent>
```