---
title: LifetimeComponent Documentation
source: https://noita.wiki.gg/wiki/Documentation:LifetimeComponent
category: modding-wiki
---

# LifetimeComponent Documentation

This page details the `LifetimeComponent` in Noita, a crucial component for managing the duration and behavior of entities. Understanding and modifying this component is essential for creating mods that involve timed effects, temporary entities, or entities that disappear after a certain period.

## Overview

The `LifetimeComponent` is attached to entities to control how long they persist in the game world. It allows for the definition of a lifespan, after which the entity will be destroyed. This is fundamental for implementing various gameplay mechanics, such as projectiles with limited flight time, temporary buffs, or environmental effects that fade away.

## Component Properties

The `LifetimeComponent` has several properties that can be configured to control its behavior. These properties are typically defined within an entity's XML definition.

### `lifetime`

This property defines the total duration of the entity's existence in seconds. Once this time elapses, the entity will be destroyed.

*   **Type:** Float
*   **Default:** Varies depending on the entity.

**Example:**

```xml
<LifetimeComponent
    lifetime="5.0"
    >
</LifetimeComponent>
```

This example sets the entity's lifetime to 5 seconds.

### `lifetime_max`

This property is often used in conjunction with `lifetime` to define a range for the entity's lifespan. The actual lifetime will be a random value between `lifetime` and `lifetime_max`.

*   **Type:** Float
*   **Default:** Varies depending on the entity.

**Example:**

```xml
<LifetimeComponent
    lifetime="3.0"
    lifetime_max="7.0"
    >
</LifetimeComponent>
```

This example sets the entity's lifetime to a random value between 3 and 7 seconds.

### `destroy_on_hit`

When set to `true`, the entity will be destroyed immediately upon taking damage, regardless of its remaining `lifetime`.

*   **Type:** Boolean
*   **Default:** `false`

**Example:**

```xml
<LifetimeComponent
    lifetime="10.0"
    destroy_on_hit="true"
    >
</LifetimeComponent>
```

This entity will be destroyed after 10 seconds or immediately if it's hit.

### `destroy_on_death`

When set to `true`, the entity will be destroyed if it reaches zero health, similar to `destroy_on_hit` but specifically tied to its health reaching zero.

*   **Type:** Boolean
*   **Default:** `false`

**Example:**

```xml
<LifetimeComponent
    lifetime="15.0"
    destroy_on_death="true"
    >
</LifetimeComponent>
```

This entity will be destroyed after 15 seconds or if its health drops to zero.

### `destroy_on_consume`

When set to `true`, the entity will be destroyed if it is "consumed" by another entity or game mechanic. This is often used for projectiles that hit a target.

*   **Type:** Boolean
*   **Default:** `false`

**Example:**

```xml
<LifetimeComponent
    lifetime="2.0"
    destroy_on_consume="true"
    >
</LifetimeComponent>
```

This entity will be destroyed after 2 seconds or if it's consumed.

### `destroy_on_player_death`

When set to `true`, the entity will be destroyed if the player character dies. This is useful for temporary effects that should not persist after a player's demise.

*   **Type:** Boolean
*   **Default:** `false`

**Example:**

```xml
<LifetimeComponent
    lifetime="30.0"
    destroy_on_player_death="true"
    >
</LifetimeComponent>
```

This entity will last for 30 seconds or until the player dies.

### `destroy_on_game_start`

When set to `true`, the entity will be destroyed immediately when the game starts. This is rarely used for entities that are meant to exist in the game.

*   **Type:** Boolean
*   **Default:** `false`

**Example:**

```xml
<LifetimeComponent
    lifetime="1.0"
    destroy_on_game_start="true"
    >
</LifetimeComponent>
```

This entity will be destroyed as soon as the game loads.

### `destroy_on_load`

When set to `true`, the entity will be destroyed when the game is loaded from a save file.

*   **Type:** Boolean
*   **Default:** `false`

**Example:**

```xml
<LifetimeComponent
    lifetime="60.0"
    destroy_on_load="true"
    >
</LifetimeComponent>
```

This entity will last for 60 seconds or until the game is loaded.

### `destroy_on_new_level`

When set to `true`, the entity will be destroyed when the player transitions to a new level.

*   **Type:** Boolean
*   **Default:** `false`

**Example:**

```xml
<LifetimeComponent
    lifetime="120.0"
    destroy_on_new_level="true"
    >
</LifetimeComponent>
```

This entity will last for 120 seconds or until the player enters a new level.

### `destroy_on_death_particle_effect`

Specifies the particle effect to spawn when the entity is destroyed due to its health reaching zero.

*   **Type:** String (path to particle effect tag)
*   **Default:** None

**Example:**

```xml
<LifetimeComponent
    lifetime="5.0"
    destroy_on_death="true"
    destroy_on_death_particle_effect="data/particles/explosion_small.xml"
    >
</LifetimeComponent>
```

This entity will spawn `explosion_small.xml` particles upon death.

### `destroy_on_hit_particle_effect`

Specifies the particle effect to spawn when the entity is destroyed due to taking damage.

*   **Type:** String (path to particle effect tag)
*   **Default:** None

**Example:**

```xml
<LifetimeComponent
    lifetime="10.0"
    destroy_on_hit="true"
    destroy_on_hit_particle_effect="data/particles/hit_spark.xml"
    >
</LifetimeComponent>
```

This entity will spawn `hit_spark.xml` particles when hit.

### `destroy_on_consume_particle_effect`

Specifies the particle effect to spawn when the entity is destroyed due to being consumed.

*   **Type:** String (path to particle effect tag)
*   **Default:** None

**Example:**

```xml
<LifetimeComponent
    lifetime="3.0"
    destroy_on_consume="true"
    destroy_on_consume_particle_effect="data/particles/dissolve.xml"
    >
</LifetimeComponent>
```

This entity will spawn `dissolve.xml` particles when consumed.

## Lua Integration

The `LifetimeComponent` can also be interacted with and modified via Lua scripting. This allows for dynamic control over entity lifespans during gameplay.

### Getting the LifetimeComponent

You can access the `LifetimeComponent` of an entity using its entity ID.

```lua
local entity_id = GetUpdatedEntityID() -- Or any other method to get an entity ID
local lifetime_comp = EntityGetFirstComponent(entity_id, "LifetimeComponent")
```

### Modifying Lifetime

You can change the `lifetime` property of an existing `LifetimeComponent`.

```lua
local entity_id = GetUpdatedEntityID()
local lifetime_comp = EntityGetFirstComponent(entity_id, "LifetimeComponent")

if lifetime_comp then
    ComponentSetValue(lifetime_comp, "lifetime", 10.0) -- Set lifetime to 10 seconds
end
```

### Checking Lifetime

You can check the current remaining lifetime of an entity.

```lua
local entity_id = GetUpdatedEntityID()
local lifetime_comp = EntityGetFirstComponent(entity_id, "LifetimeComponent")

if lifetime_comp then
    local current_lifetime = ComponentGetValue(lifetime_comp, "lifetime")
    print("Current lifetime: " .. current_lifetime)
end
```

### Adding a LifetimeComponent

You can dynamically add a `LifetimeComponent` to an entity.

```lua
local entity_id = GetUpdatedEntityID()

-- Add a LifetimeComponent with a lifetime of 5 seconds
EntityAddComponent2(entity_id, "LifetimeComponent", "lifetime", 5.0)
```

## Common Use Cases in Modding

*   **Temporary Projectiles:** Give projectiles a limited flight time so they disappear if they miss their target.
*   **Timed Buffs/Debuffs:** Apply effects to the player or enemies that last for a specific duration.
*   **Environmental Hazards:** Create traps or hazards that activate for a set period.
*   **Summoned Entities:** Make summoned creatures or objects temporary.
*   **Visual Effects:** Entities that exist solely to display a visual effect for a short time.

By understanding and utilizing the `LifetimeComponent`, modders can significantly enhance the dynamic and interactive elements of their Noita creations.