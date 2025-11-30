---
title: Electric Charge Component
source: https://noita.wiki.gg/wiki/Documentation:ElectricChargeComponent
category: modding-wiki
---

# Electric Charge Component

This documentation covers the `ElectricChargeComponent` in Noita, a crucial element for understanding and manipulating electrical phenomena within the game. Modders can leverage this component to create custom electrical effects, alter existing ones, and integrate them into their mods, enhancing gameplay and introducing new mechanics.

## Overview of Electric Charge

The `ElectricChargeComponent` is responsible for managing and simulating electrical charge on entities within Noita. It dictates how entities interact with electricity, including their ability to conduct, store, and discharge electrical energy. Understanding this component is fundamental for any mod that involves electrical interactions, such as new spells, environmental hazards, or entity behaviors.

## Component Properties

The `ElectricChargeComponent` has several properties that can be configured in `.xml` files to define its behavior.

### `charge_capacity`

*   **Description:** The maximum amount of charge an entity can hold.
*   **Type:** `float`
*   **Default:** `1.0`

### `charge_transfer_rate`

*   **Description:** The speed at which charge is transferred between connected entities.
*   **Type:** `float`
*   **Default:** `1.0`

### `charge_decay_rate`

*   **Description:** The rate at which charge dissipates over time.
*   **Type:** `float`
*   **Default:** `0.1`

### `is_conductive`

*   **Description:** Determines if the entity can conduct electricity.
*   **Type:** `bool`
*   **Default:** `true`

### `is_insulator`

*   **Description:** Determines if the entity acts as an insulator, preventing charge transfer.
*   **Type:** `bool`
*   **Default:** `false`

### `charge_visual_effect`

*   **Description:** The visual effect to display when the entity is charged. This should be a string referencing a particle effect ID.
*   **Type:** `string`
*   **Default:** `""` (no effect)

## Example Usage in XML

Here's an example of how to add an `ElectricChargeComponent` to an entity in an `.xml` file:

```xml
<Entity name="my_charged_object">
    <ElectricChargeComponent
        charge_capacity="5.0"
        charge_transfer_rate="2.0"
        charge_decay_rate="0.2"
        is_conductive="true"
        is_insulator="false"
        charge_visual_effect="PARTICLE_ELECTRIC_ARC"
    />
    <!-- Other components for the entity -->
</Entity>
```

## Lua API Interaction

The `ElectricChargeComponent` can also be interacted with using Lua scripting. You can get and set charge levels, check conductivity, and trigger electrical events.

### Getting the Component

To interact with the component, you first need to get a reference to it from an entity.

```lua
local entity = GetEntity("my_charged_object") -- Assuming you have an entity with this name
local charge_component = entity.GetComponent("ElectricChargeComponent")

if charge_component then
    -- Interact with the component
end
```

### Common Lua Functions

*   `charge_component:GetCharge()`: Returns the current charge level of the entity.
*   `charge_component:SetCharge(amount)`: Sets the charge level of the entity.
*   `charge_component:AddCharge(amount)`: Adds charge to the entity.
*   `charge_component:IsConductive()`: Returns `true` if the entity is conductive, `false` otherwise.
*   `charge_component:IsInsulator()`: Returns `true` if the entity is an insulator, `false` otherwise.
*   `charge_component:TransferCharge(target_entity, amount)`: Attempts to transfer a specified amount of charge to another entity.

### Lua Example: Creating a Charged Projectile

This example demonstrates how to create a projectile that discharges electricity on impact.

```lua
-- This script would be attached to a projectile entity

local projectile_entity = GetEntity("my_electric_projectile")
local charge_component = projectile_entity.GetComponent("ElectricChargeComponent")

if charge_component then
    -- Initialize the projectile with a high charge
    charge_component:SetCharge(10.0)

    -- Function to be called on impact
    function on_impact(hit_entity, hit_position)
        if charge_component and charge_component:GetCharge() > 0 then
            -- Discharge electricity to the hit entity
            charge_component:TransferCharge(hit_entity, charge_component:GetCharge())
            -- Optionally, create a visual effect at the impact point
            SpawnParticleEffect("PARTICLE_ELECTRIC_EXPLOSION", hit_position)
        end
    end

    -- Assuming your projectile has an "OnImpact" event that can be hooked
    -- This is a simplified representation; actual hook mechanism may vary
    projectile_entity.OnImpact = on_impact
end
```

## Related Components and Concepts

*   **`DamageComponent`**: Often used in conjunction with electrical effects to deal damage.
*   **`ParticleEmitterComponent`**: Used to create visual effects for electrical discharges.
*   **`PhysicsComponent`**: Affects how entities move and interact, which can be influenced by electrical forces.
*   **`MaterialPropertyComponent`**: Can define properties that affect conductivity or resistance.

## Further Resources

*   [Lua API](https://noita.wiki.gg/wiki/Modding:_Lua_API)
*   [Entity XML Structure](https://noita.wiki.gg/wiki/Modding:_Entity_XML_Structure)
*   [Particle Effects](https://noita.wiki.gg/wiki/Modding:_Particle_Effects)