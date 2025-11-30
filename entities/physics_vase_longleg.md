---
title: Physics Vase Longleg
category: entities
---

# Physics Vase Longleg

This document describes the `physics_vase_longleg.xml` entity, a breakable prop in Noita that contains a liquid material.

## Entity Definition

The core of this entity is based on `base_item_physics.xml`, indicating it's a physics-driven item.

```xml
<Entity name="unknown" >
  <Base file="data/entities/base_item_physics.xml" >
    <!-- ... -->
  </Base>
  <!-- ... -->
</Entity>
```

## Key Components

### PhysicsImageShapeComponent

This component defines the visual representation and physical properties of the vase.

*   **`image_file`**: Specifies the sprite used for the vase.
    *   `data/props_gfx/vase2.png`
*   **`material`**: The Box2D physics material applied to the vase.
    *   `rock_box2d`

```xml
<PhysicsImageShapeComponent
  image_file="data/props_gfx/vase2.png"
  material="rock_box2d" >
</PhysicsImageShapeComponent>
```

### CameraBoundComponent

This component controls how the entity interacts with the camera's view.

*   **`max_count`**: The maximum number of these entities that can be active within the camera's range.
    *   `50`
*   **`distance`**: The maximum distance from the camera at which the entity will be processed.
    *   `500`

```xml
<CameraBoundComponent
  max_count="50"
  distance="500">
</CameraBoundComponent>
```

### MaterialInventoryComponent

This component defines the liquid contents of the vase and how they behave when the vase is damaged or destroyed.

*   **`_enabled`**: Whether this component is active.
    *   `1` (enabled)
*   **`drop_as_item`**: If set to `1`, the contents would drop as a separate item.
    *   `0` (disabled)
*   **`on_death_spill`**: If set to `1`, the contents will spill out when the entity is destroyed.
    *   `1` (enabled)
*   **`leak_on_damage_percent`**: The percentage of HP the vase must lose before its contents start leaking.
    *   `0.8` (80% damage)

#### `count_per_material_type`

Defines the specific materials and their quantities contained within the vase.

| Material | Count |
| :------- | :---- |
| `water`  | `200` |

```xml
<MaterialInventoryComponent
  _enabled="1"
  drop_as_item="0"
  on_death_spill="1"
  leak_on_damage_percent="0.8"
  >
  <count_per_material_type>
    <Material material="water" count="200"  />
  </count_per_material_type>
</MaterialInventoryComponent>
```

### DamageModelComponent

This component governs how the vase takes damage and reacts to it.

*   **`hp`**: The hit points of the vase.
    *   `1`
*   **`falling_damages`**: Whether the vase takes damage from falling.
    *   `1` (enabled)
*   **`falling_damage_damage_min` / `max`**: The minimum and maximum damage dealt by falling.
    *   `0.1` / `1.2`
*   **`falling_damage_height_min` / `max`**: The minimum and maximum heights from which falling damage is calculated.
    *   `70` / `250`
*   **`fire_damage_amount`**: The amount of damage taken from fire.
    *   `0.2`
*   **`fire_probability_of_ignition`**: The chance of igniting when exposed to fire.
    *   `10`
*   **`critical_damage_resistance`**: Resistance to critical damage.
    *   `1` (full resistance)

```xml
<DamageModelComponent
  air_needed="0"
  blood_material="sand_blue"
  drop_items_on_death="0"
  falling_damage_damage_max="1.2"
  falling_damage_damage_min="0.1"
  falling_damage_height_max="250"
  falling_damage_height_min="70"
  falling_damages="1"
  fire_damage_amount="0.2"
  fire_probability_of_ignition="10"
  critical_damage_resistance="1"
  hp="1"
  is_on_fire="0"
  materials_create_messages="0"
  materials_damage="0"
  ragdoll_filenames_file=""
  ragdoll_material=""
  ui_report_damage="0"
  >
</DamageModelComponent>
```

### LuaComponent

This component allows for custom scripting to be attached to the entity.

*   **`_enabled`**: Whether this component is active.
    *   `1` (enabled)
*   **`script_damage_received`**: The path to the Lua script executed when the entity receives damage.
    *   `data/scripts/props/physics_vase_damage.lua`
*   **`remove_after_executed`**: If `1`, the Lua component is removed after its script finishes execution.
    *   `1`

```xml
<LuaComponent
  _enabled="1"
  script_damage_received="data/scripts/props/physics_vase_damage.lua"
  remove_after_executed="1"
  >
</LuaComponent>
```