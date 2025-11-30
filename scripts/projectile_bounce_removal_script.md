---
title: Projectile Bounce Removal Script
category: scripts
---

---

# Projectile Bounce Removal Script

This script modifies projectile behavior to prevent them from bouncing. It's designed to be attached to a projectile entity.

## Purpose

The primary function of this script is to disable the bouncing behavior of a projectile. This is achieved by setting specific properties of the `ProjectileComponent`.

## Key Components and Attributes

The script interacts with the `ProjectileComponent` of an entity. The most relevant attributes modified are:

### `ProjectileComponent`

*   **`bounce_always`**: This boolean attribute controls whether the projectile will always bounce. Setting it to `false` disables this behavior.
*   **`bounces_left`**: This integer attribute tracks the remaining number of bounces a projectile can perform. Setting it to `0` ensures no bounces can occur.

## Usage

This script should be added as a component to a projectile entity. When the projectile is spawned, this script will execute, modifying its `ProjectileComponent` to prevent any bouncing.

### Example Implementation (Conceptual)

While the provided Lua code is the core logic, in Noita's modding context, you would typically associate this script with a projectile entity definition.

```lua
-- Example of how this script might be referenced in an entity config
-- (This is illustrative and not directly from the source file)

-- projectile_config.xml
<entity name="my_non_bouncing_projectile">
    <components>
        <ProjectileComponent
            damage="10"
            speed="50"
            lifetime="2"
            bounce_always="true"  -- Initially set to true, but will be overridden
            bounces_left="5"      -- Initially set to 5, but will be overridden
        />
        <ScriptComponent
            script_filename="data/scripts/projectiles/remove_bounce.lua"
        />
    </components>
</entity>
```

## Script Logic Breakdown

1.  **`dofile_once("data/scripts/lib/utilities.lua")`**: Imports utility functions, likely for entity manipulation.
2.  **`local entity_id = GetUpdatedEntityID()`**: Gets the unique identifier for the current entity being processed.
3.  **`local x, y = EntityGetTransform( entity_id )`**: Retrieves the position of the entity (though `x` and `y` are not used in this specific script).
4.  **`entity_id = EntityGetRootEntity( entity_id )`**: Gets the root entity of the current entity. This is important as components are often attached to the root.
5.  **`if ( entity_id ~= NULL_ENTITY ) then ... end`**: Checks if a valid root entity was found.
6.  **`edit_component( entity_id, "ProjectileComponent", function(comp,vars) ... end)`**: This is the core modification function. It targets the `ProjectileComponent` of the `entity_id`.
    *   **`ComponentSetValue2( comp, "bounce_always", false )`**: Sets the `bounce_always` property to `false`.
    *   **`ComponentSetValue2( comp, "bounces_left", 0 )`**: Sets the `bounces_left` property to `0`.