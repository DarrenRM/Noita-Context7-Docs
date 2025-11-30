---
title: Noita Reactions Documentation for AI-Assisted Modding
source: https://noita.wiki.gg/wiki/Documentation:Reaction
category: modding-wiki
---

# Noita Reactions Documentation for AI-Assisted Modding

This documentation explains the "Reaction" system in Noita, a core mechanic that governs how entities interact with each other and the environment. Understanding reactions is crucial for modders to create dynamic and emergent gameplay by defining custom interactions between spells, enemies, materials, and more.

## Understanding Reactions

Reactions are the fundamental system in Noita that dictates how different elements and entities behave when they come into contact or are affected by certain conditions. This system is primarily driven by XML definitions and can be extended and manipulated through Lua scripting. By understanding and modifying these reactions, modders can introduce entirely new gameplay mechanics, alter existing ones, and create complex emergent behaviors.

### How Reactions Work

Reactions are triggered by specific conditions and result in defined outcomes. These outcomes can range from simple visual effects to complex entity transformations or damage applications. The system is designed to be modular, allowing for a vast array of potential interactions.

### Key Concepts

*   **Entity:** Any object or character in the game world (e.g., player, enemy, spell projectile, material).
*   **Component:** A piece of data attached to an entity that defines its properties or behaviors. Reactions often target specific components.
*   **Tag:** A label assigned to entities or components that helps in identifying them for reaction purposes.
*   **Action:** The effect that occurs when a reaction is triggered.
*   **Condition:** The specific circumstances that must be met for a reaction to occur.

## Reaction Definitions (XML)

The core of the reaction system is defined in XML files. These files specify the conditions under which reactions occur and the resulting actions.

### `data/reactions.xml`

This is the primary file where reaction definitions are located. Modders can add to or modify this file to introduce new reactions.

#### Structure of a Reaction Definition

A typical reaction definition in `reactions.xml` follows this structure:

```xml
<reaction
    name="[unique_reaction_name]"
    id="[unique_reaction_id]"
    >
    <condition
        name="[condition_type]"
        [condition_parameters]
        >
        <entity_tag value="[tag_name]" />
        <entity_component value="[component_name]" />
        <!-- More conditions can be nested -->
    </condition>
    <action
        name="[action_type]"
        [action_parameters]
        >
        <entity_tag value="[tag_name]" />
        <entity_component value="[component_name]" />
        <!-- More actions can be nested -->
    </action>
    <!-- Multiple conditions and actions can be defined -->
</reaction>
```

#### Common Condition Types

*   `IsTouching`: Triggers when two entities are in contact.
*   `HasComponent`: Triggers if an entity possesses a specific component.
*   `HasTag`: Triggers if an entity has a specific tag.
*   `IsMaterial`: Triggers if an entity is a specific material.
*   `IsAlive`: Triggers if an entity is alive.
*   `IsDamageType`: Triggers if the incoming damage is of a specific type.

#### Common Action Types

*   `Damage`: Applies damage to an entity.
*   `AddMaterial`: Adds a material to an entity or the environment.
*   `Destroy`: Destroys an entity.
*   `SpawnEntity`: Spawns a new entity.
*   `SetComponent`: Modifies a component's properties.
*   `PlayEffect`: Plays a visual or auditory effect.
*   `TransformToMaterial`: Transforms an entity into a different material.

#### Example Reaction: Water + Electricity

This example shows a simplified reaction where touching water with an electrical tag applies damage.

```xml
<reaction name="water_electricity_damage" id="1000001">
    <condition name="IsTouching">
        <entity_tag value="water" />
        <entity_tag value="electricity" />
    </condition>
    <action name="Damage">
        <entity_tag value="water" /> <!-- Damage the entity tagged as water -->
        <param name="damage" value="5" />
        <param name="damage_type" value="electric" />
    </action>
</reaction>
```

### Modifying Existing Reactions

To modify an existing reaction, you can:

1.  **Identify the reaction:** Find the `name` or `id` of the reaction in `data/reactions.xml`.
2.  **Override or extend:** In your mod's `data/reactions.xml`, you can either completely override the original reaction by using the same `name` and `id`, or you can add new conditions/actions to it if the game's system allows for such extensions (often by adding new `<reaction>` blocks with the same `id` but different content, though this can be complex and might not always work as expected for all reaction types). A safer approach is often to create a new reaction that *mimics* the original and adds your desired effects.

## Reaction System in Lua

While XML defines the core reactions, Lua scripting allows for more dynamic control and the creation of complex, context-aware interactions.

### Accessing Reaction Data

You can access and manipulate game entities and their components using the Lua API. This allows you to check for conditions that might trigger reactions or to manually apply effects that are part of reactions.

### Triggering Reactions Programmatically

You can use Lua functions to simulate or trigger reactions. For example, you might want to apply damage to an entity based on certain conditions you've checked in your Lua script.

#### Example: Applying Damage via Lua

```lua
-- Assuming 'entity' is a valid entity object
local damage_amount = 10
local damage_type = "fire"

-- This is a simplified example. Actual damage application might involve
-- finding the appropriate component or using a specific API function.
-- For direct reaction simulation, you might need to interact with the
-- entity's components or use internal game functions if exposed.

-- A more direct way to apply damage might be through a component method:
if entity and entity.Damage then
    entity:Damage(damage_amount, damage_type)
else
    print("Entity does not have a Damage component or is invalid.")
end

-- Alternatively, if you want to trigger a specific reaction definition:
-- This is more advanced and might require knowledge of internal game functions
-- or specific modding frameworks that expose such capabilities.
-- For instance, if there was a function like:
-- Game.TriggerReaction(entity1, entity2, "reaction_name")
-- you would use that. However, such direct functions are not always exposed.
```

### Custom Reaction Logic

Modders can create entirely new reaction-like behaviors in Lua by:

1.  **Using game loops:** Hook into game update loops (e.g., `Game.OnUpdate`) to check for custom conditions.
2.  **Spawning entities with specific components/tags:** Create entities that, when interacting with others, trigger your custom logic.
3.  **Modifying entity components:** Directly alter components to change how entities react to game events.

## Important Tags and Components for Reactions

Understanding common tags and components is key to effectively defining and manipulating reactions.

### Common Entity Tags

| Tag        | Description                                     |
| :--------- | :---------------------------------------------- |
| `water`    | Represents water entities or materials.         |
| `fire`     | Represents fire entities or materials.          |
| `electric` | Represents electrical entities or effects.      |
| `poison`   | Represents poison entities or effects.          |
| `ice`      | Represents ice entities or materials.           |
| `blood`    | Represents blood entities or materials.         |
| `fungus`   | Represents fungal entities or materials.        |
| `meat`     | Represents meat entities or materials.          |
| `oil`      | Represents oil entities or materials.           |
| `acid`     | Represents acid entities or materials.          |
| `gas`      | Represents gaseous entities or materials.       |
| `enemy`    | General tag for enemy entities.                 |
| `player`   | Tag for the player entity.                      |
| `projectile` | Tag for projectile entities.                  |
| `item`     | Tag for collectible items.                      |
| `ground`   | Tag for ground materials.                       |
| `wall`     | Tag for wall materials.                         |

### Common Components Involved in Reactions

*   **`Damageable`**: Allows an entity to take damage. Reactions often target this to inflict harm.
*   **`Material`**: Defines the properties of a material (e.g., `water`, `fire`, `oil`).
*   **`Health`**: Stores the current health of an entity.
*   **`StatusEffect`**: Manages status effects applied to an entity (e.g., burning, frozen).
*   **`PhysicsBody`**: Handles physical properties like collision.
*   **`Effect`**: Used for visual and auditory effects.
*   **`SpellComponent`**: Components specific to spell projectiles.

## Useful Links for Modding Reactions

*   [Lua API](https://noita.wiki.gg/wiki/Modding:_Lua_API)
*   [Entity Components](https://noita.wiki.gg/wiki/Entity_Components)
*   [XML Structure](https://noita.wiki.gg/wiki/XML_Structure)
*   [Noita Modding Discord](https://discord.gg/noitamodding) (for community support and asking questions)