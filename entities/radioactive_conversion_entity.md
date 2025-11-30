---
title: Radioactive Conversion Entity
category: entities
---

# Radioactive Conversion Entity

This entity defines a magical effect that converts nearby materials into radioactive or cursed variants. It's designed to be a persistent effect that can spread or maintain a radioactive zone.

## Core Components

### LifetimeComponent

*   **lifetime**: `14`
    *   Determines how long the entity exists before being removed. In this case, it's set to 14 seconds.

### MagicConvertMaterialComponent

This component is responsible for the material conversion. The entity has multiple instances of this component, each targeting different material types.

#### Component 1: Solid Conversion

*   **kill_when_finished**: `0`
    *   The entity will not be removed after this conversion is complete.
*   **from_material_tag**: `[solid]`
    *   Targets any material tagged as `[solid]`.
*   **to_material**: `rock_static_cursed_green`
    *   Converts the targeted solid materials into `rock_static_cursed_green`.
*   **steps_per_frame**: `5`
    *   Controls the speed of the conversion process.
*   **clean_stains**: `0`
    *   Does not remove stains during conversion.
*   **is_circle**: `1`
    *   The conversion area is circular.
*   **radius**: `70`
    *   The radius of the circular conversion area.
*   **loop**: `0`
    *   This conversion effect runs once.

#### Component 2: Liquid Conversion (General)

*   **kill_when_finished**: `0`
    *   The entity will not be removed after this conversion is complete.
*   **from_material_tag**: `[liquid]`
    *   Targets any material tagged as `[liquid]`.
*   **to_material**: `cursed_liquid`
    *   Converts the targeted liquid materials into `cursed_liquid`.
*   **steps_per_frame**: `5`
    *   Controls the speed of the conversion process.
*   **clean_stains**: `0`
    *   Does not remove stains during conversion.
*   **is_circle**: `1`
    *   The conversion area is circular.
*   **radius**: `70`
    *   The radius of the circular conversion area.
*   **loop**: `1`
    *   This conversion effect will loop continuously.

#### Component 3: Sand Ground Conversion

*   **kill_when_finished**: `0`
    *   The entity will not be removed after this conversion is complete.
*   **from_material_tag**: `[sand_ground]`
    *   Targets materials tagged as `[sand_ground]`.
*   **to_material**: `cursed_liquid`
    *   Converts the targeted sand ground materials into `cursed_liquid`.
*   **steps_per_frame**: `5`
    *   Controls the speed of the conversion process.
*   **clean_stains**: `0`
    *   Does not remove stains during conversion.
*   **is_circle**: `1`
    *   The conversion area is circular.
*   **radius**: `70`
    *   The radius of the circular conversion area.
*   **loop**: `1`
    *   This conversion effect will loop continuously.

#### Component 4: Sand Other Conversion

*   **kill_when_finished**: `0`
    *   The entity will not be removed after this conversion is complete.
*   **from_material_tag**: `[sand_other]`
    *   Targets materials tagged as `[sand_other]`.
*   **to_material**: `cursed_liquid`
    *   Converts the targeted sand materials into `cursed_liquid`.
*   **steps_per_frame**: `5`
    *   Controls the speed of the conversion process.
*   **clean_stains**: `0`
    *   Does not remove stains during conversion.
*   **is_circle**: `1`
    *   The conversion area is circular.
*   **radius**: `70`
    *   The radius of the circular conversion area.
*   **loop**: `1`
    *   This conversion effect will loop continuously.

## AI Modding Considerations

*   **Targeting Specific Materials**: To modify which materials are converted, adjust the `from_material_tag` and `to_material` attributes. You can use existing material tags or define custom ones.
*   **Conversion Radius and Speed**: The `radius` and `steps_per_frame` attributes directly influence the area and intensity of the conversion. Larger radii and higher steps per frame will create more significant and faster changes.
*   **Persistence**: Setting `loop="1"` on `MagicConvertMaterialComponent` makes the conversion effect continuous. Setting `kill_when_finished="0"` on the `LifetimeComponent` (if it were present and controlling the entity's lifespan) would also be crucial for persistent effects. In this case, the `LifetimeComponent` is short, but the `MagicConvertMaterialComponent`s are set to loop, implying the entity might be spawned by another mechanism that manages its overall duration.
*   **Custom Effects**: This entity serves as a template for creating custom environmental hazards or transformations. You could, for example, create an entity that converts normal rock to radioactive sludge or vice-versa.