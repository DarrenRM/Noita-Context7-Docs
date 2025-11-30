---
title: Modding: Making a Custom Enemy
source: https://noita.wiki.gg/wiki/Modding:_Making_a_custom_enemy
category: modding-wiki
---

# Modding: Making a Custom Enemy

This documentation provides a foundational guide to creating custom enemies in Noita. Understanding enemy components and their associated tags is crucial for defining enemy behavior, interactions, and overall presence within the game world.

## Core Components and Tags for Custom Enemies

To create a custom enemy, you'll primarily work with XML files to define its properties and behaviors. This involves assigning specific components and tags to the enemy entity.

### Essential Components

These components are fundamental for defining an enemy's core functionality.

| Component                                                              | Purpose                                                                                             |
| :--------------------------------------------------------------------- | :-------------------------------------------------------------------------------------------------- |
| [AnimalAIComponent](https://noita.wiki.gg/wiki/Documentation:_AnimalAIComponent) | Governs enemy behavior, including movement patterns and attack strategies.                            |
| [DamageModelComponent](https://noita.wiki.gg/wiki/Documentation:_DamageModelComponent) | Enables the enemy to take damage, defines its damage multipliers, and its weaknesses to specific materials. |
| [PathFindingComponent](https://noita.wiki.gg/wiki/Documentation:_PathFindingComponent) | Allows the enemy to navigate through terrain and interact with other entities.                      |
| [PathFindingGridMarkerComponent](https://noita.wiki.gg/wiki/Documentation:_PathFindingGridMarkerComponent) | Influences the path-finding grid. Documentation is limited and requires further research.          |
| [CharacterPlatformingComponent](https://noita.wiki.gg/wiki/Documentation:_CharacterPlatformingComponent) | Controls the enemy's movement capabilities, such as jumping and walking.                            |
| [CharacterDataComponent](https://noita.wiki.gg/wiki/Documentation:_CharacterDataComponent) | Affects the enemy's collision detection, physics, and other physical properties.                    |
| [HitboxComponent](https://noita.wiki.gg/wiki/Documentation:_HitboxComponent) | Defines the enemy's hitbox, which determines where attacks and other interactions will register.    |
| [CameraBoundComponent](https://noita.wiki.gg/wiki/Documentation:_CameraBoundComponent) | Manages the distance from the camera at which the enemy entity will be unloaded from memory.      |
| [SpriteComponent](https://noita.wiki.gg/wiki/Documentation:_SpriteComponent) | Specifies the visual sprite graphics used for the enemy.                                           |
| [SpriteAnimatorComponent](https://noita.wiki.gg/wiki/Documentation:_SpriteAnimatorComponent) | Handles sprite animation, allowing the enemy to transition between different visual states (e.g., idle, walking, attacking). |
| [AudioComponent](https://noita.wiki.gg/wiki/Documentation:_AudioComponent) | Determines the audio cues played during specific enemy events, such as attacks or taking damage.    |

### Key Entity Tags

Tags are used to categorize entities and grant them specific properties or behaviors.

| Tag                      | Purpose                                                                                             |
| :----------------------- | :-------------------------------------------------------------------------------------------------- |
| `mortal`                 | A general tag for living creatures and entities that can be destroyed. (Requires further research.) |
| `hittable`               | Indicates that the enemy can be hit by attacks.                                                     |
| `enemy`                  | Marks the entity as an enemy.                                                                       |
| `flying`                 | Designates the enemy as a flying entity.                                                            |
| `boss`                   | Identifies the enemy as a boss character.                                                           |
| `miniboss`               | Identifies the enemy as a mini-boss character.                                                      |
| `human`                  | (Requires further research.)                                                                        |
| `prey`                   | Allows predators to target this enemy.                                                              |
| `homing_target`          | Enables the enemy to be tracked by homing projectiles.                                              |
| `destruction_target`     | Makes the enemy a target for the [Destruction](https://noita.wiki.gg/wiki/Destruction) spell.       |
| `teleportable_NOT`       | Prevents the enemy from being teleported.                                                           |
| `polymorphable_NOT`      | Prevents the enemy from being polymorphed.                                                          |
| `necrobot_NOT`           | Prevents the enemy from being revived by entities like [Necrobot](https://noita.wiki.gg/wiki/Necrobot). |
| `glue_NOT`               | Prevents the enemy from being affected by glue.                                                     |
| `curse_NOT`              | Grants immunity to venomous curse effects. Does not grant immunity to curse damage.                 |
| `touchmagic_immunity`    | Grants immunity to [Touch of](https://noita.wiki.gg/wiki/Touch_of) spells.                          |

## Understanding AnimalAIComponent States

The `AnimalAIComponent` utilizes an `ai_state` enum to define its current behavior. These states range from 1 to 21 and correspond to specific actions.

```lua
local states = {
 "RandomMove",
 "Wandering",
 "Eating",
 "RaisingHead",
 "PreparingJump",
 "MoveNearTarget",
 "Peeing",
 "Defecating",
 "Alert",
 "Landing",
 "TakingFireDamage",
 "EscapingPrey",
 "AttackingMelee",
 "AttackingMeleeDash",
 "AttackingRanged",
 "AttackingRangedMulti",
 "Escaping",
 "JobDefault",
 "JobGoto",
 "JobHelpOtherEntity",
 "GoNearHome",
}
```

You can retrieve and print the current state of an `AnimalAIComponent` using the following Lua script:

```lua
local animal = GetUpdatedEntityID()
local state = ComponentGetValue2(
  EntityGetFirstComponentIncludingDisabled(animal, "AnimalAIComponent"), "ai_state"
)

print(states[state])
```