---
title: Noita Item Components for AI-Assisted Modding
source: https://noita.wiki.gg/wiki/Documentation:ItemComponent
category: modding-wiki
---

# Noita Item Components for AI-Assisted Modding

This documentation provides a comprehensive overview of Noita's Item Components, the fundamental building blocks that define the behavior and properties of items within the game. Understanding these components is crucial for modders, as they allow for the creation of new items, modification of existing ones, and the implementation of complex gameplay mechanics through AI-assisted modding workflows.

## Understanding Item Components

Item Components are the core of Noita's item system. They are attached to item entities and dictate everything from an item's visual appearance and sound effects to its magical properties, combat abilities, and interactions with the game world. By manipulating these components, modders can achieve a vast range of customization.

### How Components Work

Each item in Noita is essentially a collection of one or more components. These components are defined in XML files and can be dynamically added, removed, or modified through Lua scripting. This modular design makes the item system highly flexible and extensible.

### Component Structure

Components typically have a set of parameters that can be configured. These parameters control specific aspects of the component's functionality. For example, a `DamageComponent` might have parameters for damage amount, damage type, and knockback.

## Common Item Components and Their Usage

This section details frequently used item components and provides examples of how they can be applied in modding.

### `DamageComponent`

This component defines the damage an item can inflict.

| Parameter | Type   | Description                                     | Default |
| :-------- | :----- | :---------------------------------------------- | :------ |
| damage    | float  | The base damage value.                          | 10      |
| damage_type | string | The type of damage (e.g., "physical", "magic"). | "physical" |
| knockback | float  | The force of knockback applied.                 | 1       |

**Example:**

```xml
<ItemComponent component_name="DamageComponent" damage="25" damage_type="magic" knockback="5"/>
```

### `HealingComponent`

This component allows an item to restore health.

| Parameter | Type   | Description                               | Default |
| :-------- | :----- | :---------------------------------------- | :------ |
| heal_amount | float  | The amount of health to restore.          | 10      |
| heal_percentage | bool | If true, `heal_amount` is a percentage. | false   |

**Example:**

```xml
<ItemComponent component_name="HealingComponent" heal_amount="50" heal_percentage="true"/>
```

### `ManaComponent`

This component relates to mana regeneration or consumption.

| Parameter | Type   | Description                                     | Default |
| :-------- | :----- | :---------------------------------------------- | :------ |
| mana_gain | float  | The amount of mana gained.                      | 0       |
| mana_cost | float  | The amount of mana consumed.                    | 0       |

**Example:**

```xml
<ItemComponent component_name="ManaComponent" mana_gain="5"/>
```

### `ProjectileComponent`

This component enables an item to fire projectiles.

| Parameter | Type   | Description                                                              | Default |
| :-------- | :----- | :----------------------------------------------------------------------- | :------ |
| projectile_file | string | The path to the projectile's entity file.                                |         |
| speed     | float  | The speed of the projectile.                                             | 100     |
| lifetime  | float  | The duration the projectile exists before disappearing.                  | 5       |
| damage    | float  | The damage the projectile inflicts (can override `DamageComponent`).     |         |
| knockback | float  | The knockback the projectile inflicts (can override `DamageComponent`).  |         |

**Example:**

```xml
<ItemComponent component_name="ProjectileComponent" projectile_file="data/entities/projectiles/magic_missile.xml" speed="150" lifetime="7"/>
```

### `AreaOfEffectComponent`

This component creates an area of effect when the item is used or activated.

| Parameter | Type   | Description                                                              | Default |
| :-------- | :----- | :----------------------------------------------------------------------- | :------ |
| radius    | float  | The radius of the area of effect.                                        | 50      |
| damage    | float  | The damage dealt within the area of effect.                              |         |
| damage_type | string | The type of damage dealt within the area of effect.                      | "physical" |
| knockback | float  | The knockback applied within the area of effect.                         |         |
| effect_entity | string | The path to an entity to spawn at the center of the AoE (e.g., for visual effects). |         |

**Example:**

```xml
<ItemComponent component_name="AreaOfEffectComponent" radius="75" damage="30" damage_type="fire" effect_entity="data/entities/particles/fire_explosion.xml"/>
```

### `StatusEffectComponent`

This component applies status effects to targets.

| Parameter | Type   | Description                                                              | Default |
| :-------- | :----- | :----------------------------------------------------------------------- | :------ |
| status_effect | string | The name of the status effect to apply (e.g., "burning", "poisoned"). |         |
| duration  | float  | The duration of the status effect in seconds.                            | 5       |
| chance    | float  | The chance (0.0 to 1.0) of applying the status effect.                   | 1.0     |

**Example:**

```xml
<ItemComponent component_name="StatusEffectComponent" status_effect="burning" duration="10" chance="0.75"/>
```

### `MaterialComponent`

This component defines the material properties of an item, affecting its interaction with the environment (e.g., melting, freezing).

| Parameter | Type   | Description                                                              | Default |
| :-------- | :----- | :----------------------------------------------------------------------- | :------ |
| material  | string | The material type (e.g., "wood", "metal", "ice").                        | "wood"  |
| melt_temperature | float | The temperature at which the material melts.                             |         |
| freeze_temperature | float | The temperature at which the material freezes.                           |         |

**Example:**

```xml
<ItemComponent component_name="MaterialComponent" material="ice" freeze_temperature="-10"/>
```

### `InventoryComponent`

This component allows an item to act as a container or to be placed in an inventory.

| Parameter | Type   | Description                                                              | Default |
| :-------- | :----- | :----------------------------------------------------------------------- | :------ |
| capacity  | int    | The maximum number of items this inventory can hold.                     | 0       |
| can_take_items | bool | Whether other items can be placed into this inventory.                   | true    |
| can_drop_items | bool | Whether items can be taken out of this inventory.                        | true    |

**Example:**

```xml
<ItemComponent component_name="InventoryComponent" capacity="5" can_take_items="true"/>
```

### `PickableComponent`

This component makes an item collectible by the player.

| Parameter | Type   | Description                                                              | Default |
| :-------- | :----- | :----------------------------------------------------------------------- | :------ |
| pickable | bool | Whether the item can be picked up.                                       | true    |

**Example:**

```xml
<ItemComponent component_name="PickableComponent" pickable="true"/>
```

### `SpriteComponent`

This component defines the visual appearance of an item.

| Parameter | Type   | Description                                                              | Default |
| :-------- | :----- | :----------------------------------------------------------------------- | :------ |
| sprite | string | The path to the sprite file.                                             |         |
| default_animation | string | The default animation to play.                                           |         |

**Example:**

```xml
<ItemComponent component_name="SpriteComponent" sprite="data/sprites/items/potion_healing.xml" default_animation="idle"/>
```

### `LuaComponent`

This component allows for custom behavior defined in Lua scripts.

| Parameter | Type   | Description                                                              | Default |
| :-------- | :----- | :----------------------------------------------------------------------- | :------ |
| script_path | string | The path to the Lua script file.                                         |         |

**Example:**

```xml
<ItemComponent component_name="LuaComponent" script_path="data/scripts/items/custom_wand_behavior.lua"/>
```

## Creating and Modifying Items

Modding items in Noita primarily involves creating or modifying XML files that define item entities. These XML files reference the components that give the item its properties.

### Item Entity XML Structure

A typical item entity XML file looks like this:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<Entity name="MyCustomItem">
    <ItemComponent
        item_name="$custom_item_name"
        description="$custom_item_description"
        tags="consumable,magic"
    />
    <SpriteComponent
        sprite="data/sprites/items/my_custom_item.xml"
        default_animation="idle"
    />
    <DamageComponent
        damage="20"
        damage_type="magic"
        knockback="3"
    />
    <LuaComponent
        script_path="data/scripts/items/my_custom_item_logic.lua"
    />
</Entity>
```

### Adding New Items

To add a new item, you would typically:

1.  **Create a new XML file** in the `data/entities/items/` directory (or a subdirectory within it).
2.  **Define the `Entity` tag** with a unique name.
3.  **Add an `ItemComponent`** to define basic item properties like name, description, and tags.
4.  **Add other relevant components** (e.g., `SpriteComponent`, `DamageComponent`, `LuaComponent`) to define its behavior and appearance.
5.  **Ensure the item is registered** in the game's item database or through a Lua script that spawns it.

### Modifying Existing Items

To modify an existing item, you can:

1.  **Locate the item's XML file** in the game's data directory.
2.  **Copy the file** to your mod's `data/entities/items/` directory.
3.  **Edit the components** within the copied XML file to change its properties. For example, to increase the damage of a specific wand, you would find its XML and modify the `DamageComponent`.

## Advanced Concepts and AI Integration

AI can be leveraged to assist in various aspects of item component modding.

### AI-Assisted Component Generation

AI models can be trained on existing Noita item component XML to generate new component configurations based on natural language prompts. For example, a prompt like "Create a component for a potion that heals 75% of health and has a 50% chance to apply a temporary speed boost" could be used to generate the relevant XML.

### AI for Scripting Logic

For `LuaComponent`s, AI can help generate Lua code snippets or even full scripts based on desired item behaviors. This is particularly useful for complex interactions that might be difficult to script manually.

### AI for Balancing and Testing

AI can simulate gameplay scenarios to test the balance of new items and their components, identifying potential exploits or underpowered mechanics before they are implemented in-game.

## Useful Links and Resources

*   [Lua API](https://noita.wiki.gg/wiki/Modding:_Lua_API)
*   [Noita Modding Discord](https://discord.gg/noitamodding) (for community support and discussion)
*   [Noita Wiki Modding Section](https://noita.wiki.gg/wiki/Category:Modding)

## Component Reference (Partial List)

This is a non-exhaustive list of common components. Many more exist, and their parameters can be explored by examining the game's internal data files.

*   `ActionComponent`
*   `AnimationComponent`
*   `AudioComponent`
*   `ChargeableComponent`
*   `CollisionComponent`
*   `ConsumeComponent`
*   `DamageAreaComponent`
*   `DecalComponent`
*   `DestroyAfterDurationComponent`
*   `DrunkComponent`
*   `EffectComponent`
*   `EmittingComponent`
*   `ExplosionComponent`
*   `ForceFieldComponent`
*   `GravityComponent`
*   `HealthComponent`
*   `ImmunityComponent`
*   `LightComponent`
*   `LimitedUsesComponent`
*   `MaterialItemComponent`
*   `MovementComponent`
*   `ParticleEmitterComponent`
*   `PhysicsComponent`
*   `PlayerComponent`
*   `PoisonComponent`
*   `ProjectileComponent`
*   `RandomComponent`
*   `RagdollComponent`
*   `RechargeComponent`
*   `RenderComponent`
*   `RootComponent`
*   `SellComponent`
*   `ShieldComponent`
*   `SoundEmitterComponent`
*   `SpawnComponent`
*   `SpellComponent`
*   `StatComponent`
*   `SteeringComponent`
*   `StunComponent`
*   `TeleportComponent`
*   `TimedExplosionComponent`
*   `TransformComponent`
*   `TriggerComponent`
*   `UIComponent`
*   `VelocityComponent`
*   `VulnerabilityComponent`
*   `WandComponent`
*   `WaterComponent`
*   `WispComponent`