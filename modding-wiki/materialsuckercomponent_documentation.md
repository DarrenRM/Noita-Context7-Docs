---
title: MaterialSuckerComponent Documentation
source: https://noita.wiki.gg/wiki/Documentation:MaterialSuckerComponent
category: modding-wiki
---

# MaterialSuckerComponent Documentation

This documentation covers the `MaterialSuckerComponent` in Noita, a crucial component for creating entities that can absorb and store materials. Understanding this component is essential for modders looking to implement custom mechanics involving material collection, transformation, or consumption.

## Overview

The `MaterialSuckerComponent` allows an entity to act as a "sucker" for specific materials. It defines which materials the entity can absorb, how much it can store, and what happens to the absorbed materials. This is fundamental for creating custom items, enemies, or environmental effects that interact with the game's material system.

## Component Properties

The `MaterialSuckerComponent` has several properties that can be configured in an entity's XML definition.

### `material_to_suck`

*   **Type:** String
*   **Description:** The specific material ID that this component will attempt to suck.
*   **Example:** `"WATER"`, `"LAVA"`, `"POISON"`

### `suck_radius`

*   **Type:** Float
*   **Description:** The radius around the entity within which it will attempt to suck the specified material.
*   **Example:** `5.0`

### `suck_speed`

*   **Type:** Float
*   **Description:** The rate at which the material is sucked. Higher values mean faster absorption.
*   **Example:** `1.0`

### `max_material_amount`

*   **Type:** Float
*   **Description:** The maximum amount of the `material_to_suck` that the entity can store.
*   **Example:** `100.0`

### `material_storage_component_name`

*   **Type:** String
*   **Description:** The name of a `MaterialStorageComponent` that this `MaterialSuckerComponent` will interact with. If not specified, the sucker will manage its own internal storage (though this is less common for complex interactions).
*   **Example:** `"my_custom_storage"`

### `suck_only_if_material_is_liquid`

*   **Type:** Boolean
*   **Description:** If `true`, the component will only suck the material if it is currently in a liquid state.
*   **Example:** `true`

### `suck_only_if_material_is_gas`

*   **Type:** Boolean
*   **Description:** If `true`, the component will only suck the material if it is currently in a gaseous state.
*   **Example:** `true`

### `suck_when_damaged`

*   **Type:** Boolean
*   **Description:** If `true`, the entity will attempt to suck materials when it takes damage.
*   **Example:** `false`

### `suck_when_hit_by_material`

*   **Type:** Boolean
*   **Description:** If `true`, the entity will attempt to suck materials when it is directly hit by the specified material.
*   **Example:** `true`

### `suck_when_nearby_material_is_above_threshold`

*   **Type:** Boolean
*   **Description:** If `true`, the entity will attempt to suck materials if the concentration of the `material_to_suck` within its `suck_radius` exceeds a certain threshold (this threshold is often implicitly handled by the game's simulation or other components).
*   **Example:** `false`

### `suck_effect_particle_emitter`

*   **Type:** String
*   **Description:** The name of a particle emitter to spawn when the material is being sucked.
*   **Example:** `"dust_particles"`

### `suck_effect_sound_file`

*   **Type:** String
*   **Description:** The path to a sound file to play when the material is being sucked.
*   **Example:** `"data/audio/sfx/suck_sound.ogg"`

## Example XML Implementation

Here's an example of how to implement a `MaterialSuckerComponent` on an entity. This example creates a simple "water collector" that absorbs water within a 5-unit radius, up to 100 units, and plays a sound effect.

```xml
<entity name="water_collector">
    <MaterialSuckerComponent
        material_to_suck="WATER"
        suck_radius="5.0"
        max_material_amount="100.0"
        suck_speed="0.5"
        suck_effect_sound_file="data/audio/sfx/water_absorb.ogg"
    />
    <!-- Other components like Position, Sprite, etc. would go here -->
</entity>
```

## Interaction with `MaterialStorageComponent`

The `MaterialSuckerComponent` is often paired with a `MaterialStorageComponent` to manage the absorbed materials. The `MaterialStorageComponent` defines the actual storage slots and their capacities.

If `material_storage_component_name` is specified in `MaterialSuckerComponent`, the sucked material will be transferred to the designated `MaterialStorageComponent`. If it's not specified, the `MaterialSuckerComponent` might manage a simple internal buffer, but for more complex modding, using a dedicated `MaterialStorageComponent` is recommended.

### Example with `MaterialStorageComponent`

```xml
<entity name="advanced_collector">
    <MaterialSuckerComponent
        material_to_suck="LAVA"
        suck_radius="7.0"
        max_material_amount="200.0"
        material_storage_component_name="lava_storage"
    />
    <MaterialStorageComponent
        name="lava_storage"
        capacity="200.0"
        material_type="LAVA"
    />
    <!-- Other components -->
</entity>
```

In this example, the `advanced_collector` entity will suck `LAVA` and store it in its `lava_storage` component, which has a capacity of 200.0 units of `LAVA`.

## Lua API Integration

While the core functionality is defined in XML, you can interact with and modify the behavior of `MaterialSuckerComponent` using the Lua API. This allows for dynamic changes to sucking behavior, conditional absorption, or triggering custom events based on material absorption.

You can access `MaterialSuckerComponent` instances attached to an entity using `Entity.GetComponent(MaterialSuckerComponent)`.

### Example Lua Snippet (Conceptual)

```lua
local entity = GetEntitySomehow() -- Replace with actual entity retrieval
local sucker_comp = entity.GetComponent(MaterialSuckerComponent)

if sucker_comp then
    -- Example: Dynamically change the material being sucked
    -- Note: This might require game logic to re-apply or re-initialize the component's behavior
    -- sucker_comp.material_to_suck = "ACID"

    -- Example: Check how much material is currently stored (if using internal storage or accessing storage component)
    -- This would typically involve accessing the associated MaterialStorageComponent
    -- local storage_comp = entity.GetComponent(MaterialStorageComponent)
    -- if storage_comp then
    --     local current_amount = storage_comp.GetAmount()
    --     print("Current stored material amount: " .. current_amount)
    -- end

    -- Example: Trigger a custom action when material is sucked
    -- This would likely involve hooking into game events or using a custom script
    -- that monitors the MaterialSuckerComponent's state or the MaterialStorageComponent's changes.
end
```

For detailed information on the Lua API and how to interact with components, refer to the [Lua API](https://noita.wiki.gg/wiki/Modding:_Lua_API).

## Important Considerations

*   **Material IDs:** Ensure you are using the correct material IDs. Refer to the [Materials](https://noita.wiki.gg/wiki/Materials) page for a comprehensive list.
*   **Component Dependencies:** The `MaterialSuckerComponent` often relies on other components like `MaterialStorageComponent` for effective material management.
*   **Performance:** Be mindful of `suck_radius` and `suck_speed` in large numbers of entities, as extensive material simulation can impact performance.
*   **Game Logic:** The actual sucking and material transfer are handled by the game's simulation loop. Modifying these components primarily configures how the game's existing systems will interact with your custom entities.