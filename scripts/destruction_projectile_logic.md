---
title: Destruction Projectile Logic
category: scripts
---

# Destruction Projectile Logic

This script defines the behavior of a projectile that causes destruction and damage to entities within its radius. It targets enemies and players, applying different effects to each.

## Core Functionality

The script identifies entities within a certain radius and applies destruction effects. It differentiates between enemies and players, with specific conditions for targeting enemies.

## Targeting and Effects

### Enemy Targeting

-   **Radius:** Enemies within 200 units of the projectile are considered.
-   **Proximity Check:** Further filtering occurs for enemies within 300 units of the projectile's origin.
-   **Exclusions:** Enemies tagged with `"boss"` or `"this_is_sampo"` are *not* targeted.
-   **Effects on Targeted Enemies:**
    -   Loads `data/entities/particles/destruction.xml` at the enemy's location.
    -   Loads `data/entities/misc/explosion_was_here.xml` at the enemy's location.
    -   Kills the targeted enemy using `EntityKill()`.

### Player Targeting

-   **Identification:** All entities tagged with `"player_unit"` are targeted.
-   **Effects on Players:**
    -   Loads `data/entities/particles/destruction.xml` at the player's location.
    -   Loads `data/entities/misc/explosion_was_here.xml` at the player's location.
    -   Applies a damage effect to the player's `DamageModelComponent`.

## Player Damage Calculation

When a player is targeted, their health (`hp`) is reduced. The damage calculation is as follows:

```lua
hp = math.max( 0.04, hp - math.max( hp * 0.075, 0.5 ) )
```

This formula ensures that:
-   The health reduction is at least 0.5 HP.
-   The health reduction is also at least 7.5% of the current HP.
-   The player's HP will not drop below 0.04.

## Global Effects

-   **Screenshake:** A screenshake effect with an intensity of 100 is triggered using `GameScreenshake( 100 )`.
-   **Projectile Self-Destruction:** The projectile itself is killed using `EntityKill( entity_id )` after its effects are applied.

## Key Functions Used

-   `GetUpdatedEntityID()`: Retrieves the ID of the current entity.
-   `EntityGetTransform()`: Gets the position (x, y) of an entity.
-   `EntityGetInRadiusWithTag()`: Finds entities within a specified radius and with a given tag.
-   `EntityGetWithTag()`: Finds all entities with a specific tag.
-   `EntityHasTag()`: Checks if an entity has a particular tag.
-   `EntityLoad()`: Loads an entity from an XML file at a given position.
-   `EntityKill()`: Destroys an entity.
-   `EntityGetComponent()`: Retrieves a component from an entity.
-   `ComponentGetValue2()`: Gets the value of a component's field.
-   `ComponentSetValue2()`: Sets the value of a component's field.
-   `math.abs()`: Calculates the absolute difference between two numbers.
-   `math.max()`: Returns the larger of two or more numbers.
-   `GameScreenshake()`: Triggers a screenshake effect.