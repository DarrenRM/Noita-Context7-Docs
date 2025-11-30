---
title: Root Grower Leaf Prop
category: entities
---

# Root Grower Leaf Prop

This document describes the `root_grower_leaf.xml` entity, a prop found in Noita.

## Core Entity

This entity represents a small, hittable prop.

```xml
<Entity tags="hittable,prop" >
    ...
</Entity>
```

## Key Components

### HitboxComponent

Defines the physical boundaries of the prop for interactions.

```xml
<HitboxComponent
    aabb_min_x="-6"
    aabb_max_x="6"
    aabb_min_y="-10"
    aabb_max_y="4" >
</HitboxComponent>
```

*   **aabb_min_x, aabb_max_x, aabb_min_y, aabb_max_y**: Define the bounding box of the prop.

### DamageModelComponent

Governs how the prop reacts to damage and environmental effects.

```xml
<DamageModelComponent
    air_needed="0"
    falling_damages="1"
    fire_damage_amount="0.9"
    fire_probability_of_ignition="0.8"
    fire_damage_ignited_amount="0.5"
    hp="0.1"
    materials_damage="1"
    materials_that_damage="acid,lava"
    materials_how_much_damage="0.004,0.004"
    blood_material="grass"
    blood_multiplier="0.1"
    physics_objects_damage="1"
    ragdoll_filenames_file="data/ragdolls/root_grower_leaf/filenames.txt"
    ragdoll_material="meat_slime_green"
    ui_report_damage="0"
    >
</DamageModelComponent>
```

*   **hp**: The health of the prop. Very low, suggesting it's easily destroyed.
*   **fire_damage_amount, fire_probability_of_ignition, fire_damage_ignited_amount**: Defines its susceptibility and reaction to fire.
*   **materials_that_damage**: Specifies materials that can damage this prop (acid, lava).
*   **materials_how_much_damage**: The damage multiplier for the specified materials.
*   **ragdoll_filenames_file**: Points to the file defining its ragdoll behavior when destroyed.
*   **ragdoll_material**: The material associated with its ragdoll.
*   **ui_report_damage**: Set to `0`, meaning it won't report damage in the UI.

### SpriteComponent

Handles the visual representation of the prop.

```xml
<SpriteComponent
    image_file="data/props_gfx/root_grower_leaf.xml"
    >
</SpriteComponent>
```

*   **image_file**: The XML file containing the sprite's graphical data.