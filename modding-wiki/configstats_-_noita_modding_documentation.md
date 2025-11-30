---
title: ConfigStats - Noita Modding Documentation
source: https://noita.wiki.gg/wiki/Documentation:impl::ConfigStats
category: modding-wiki
---

# ConfigStats - Noita Modding Documentation

This documentation page details the `ConfigStats` component in Noita, which is crucial for defining and managing the statistical properties of entities within the game. Understanding `ConfigStats` is essential for modders looking to customize entity behavior, damage, health, and other numerical attributes.

## Overview of ConfigStats

The `ConfigStats` component is a fundamental part of Noita's entity system, responsible for holding and manipulating various statistical values. These stats are used by many other game systems to determine how entities interact, their survivability, and their offensive capabilities.

### Key Concepts

*   **Stats:** Numerical values that define an entity's attributes.
*   **Components:** `ConfigStats` is a component that can be attached to entities.
*   **Modding Impact:** Modifying `ConfigStats` allows for direct control over entity power levels, resistances, and damage output.

## Using ConfigStats in Mods

While the provided source page has no text content, the existence of `impl::ConfigStats` implies its importance. In a typical Noita modding context, you would interact with `ConfigStats` through Lua scripting or by directly editing entity XML files.

### Modifying Stats via XML

Entities in Noita are often defined in XML files. The `ConfigStats` component would be declared within an entity's XML definition, allowing you to set initial stat values.

**Example (Conceptual XML Structure):**

```xml
<entity name="my_custom_enemy">
    <ConfigStats
        hp="100"
        damage="10"
        defense="5"
        mana_regen="1"
    />
    <!-- Other components -->
</entity>
```

*   `hp`: Health points of the entity.
*   `damage`: Base damage dealt by the entity.
*   `defense`: Defensive capabilities, potentially reducing incoming damage.
*   `mana_regen`: Rate at which mana regenerates (if applicable).

### Modifying Stats via Lua

Lua scripting provides a dynamic way to alter `ConfigStats` during gameplay or at entity spawn. You can access and modify these stats using the Noita Lua API.

**Example (Conceptual Lua Script):**

```lua
-- Get the entity that has this script attached
local entity = GetUpdatedEntity()

-- Get the ConfigStats component
local stats_component = entity.ConfigStats

-- Check if the component exists
if stats_component then
    -- Modify health
    stats_component.hp = stats_component.hp * 1.5 -- Increase HP by 50%

    -- Modify damage
    stats_component.damage = stats_component.damage + 5 -- Add 5 damage

    -- Add a new stat if not present (this might require specific API functions)
    -- For example, if there's a 'resistance_fire' stat:
    -- if stats_component.resistance_fire == nil then
    --     stats_component.resistance_fire = 0.2 -- 20% fire resistance
    -- end
end
```

**Note:** The exact Lua API functions and property names for `ConfigStats` would be found in the [Lua API documentation](https://noita.wiki.gg/wiki/Modding:_Lua_API).

## Common Stats and Their Usage

While specific stat names can vary and are often defined by the game's internal systems, here are some commonly encountered statistical concepts managed by `ConfigStats`:

*   **Health (hp):** The entity's life points. When `hp` reaches zero, the entity is typically destroyed.
*   **Damage (damage):** The base offensive power of the entity. This value is often modified by damage types and other factors.
*   **Defense/Armor (defense):** A stat that can reduce incoming damage. The exact implementation (flat reduction, percentage reduction) depends on the game's internal logic.
*   **Speed (speed):** Affects movement speed.
*   **Mana (mana):** For entities that use magic, this represents their magical energy.
*   **Mana Regeneration (mana_regen):** The rate at which mana is restored.
*   **Resistances/Vulnerabilities:** Stats that modify damage taken from specific damage types (e.g., `resistance_fire`, `vulnerability_ice`).

## Further Modding Resources

*   [Modding:Lua API](https://noita.wiki.gg/wiki/Modding:_Lua_API)
*   [Modding:Entity Documentation](https://noita.wiki.gg/wiki/Modding:_Entity_Documentation) (General entity structure)