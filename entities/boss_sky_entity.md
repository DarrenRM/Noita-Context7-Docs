---
title: Boss Sky Entity
category: entities
---

# Boss Sky Entity

This document describes the `boss_sky.lua` entity, which defines the behavior and properties of the Sky Boss in Noita. This entity is designed to be a challenging encounter, interacting with the player's health and positioning.

## Key Attributes and Behaviors

### Initialization (`init` function)

*   **Player Health Sync:** The boss's maximum and current HP are synchronized with the player's HP at the time of initialization. This ensures the boss presents a relevant challenge.
*   **Starting Y-Position:** Stores the initial Y-coordinate of the boss. This is used later for teleportation mechanics.

### Damage Handling (`damage_received` function)

*   **Damage Reflection:** When the boss receives damage, it calculates the player's remaining HP percentage.
*   **Damage Apparition:** A separate entity (`boss_sky_damage.xml`) is spawned at the boss's location, carrying the calculated HP percentage. This likely visualizes or applies a debuff related to the boss's remaining health.
*   **Music Tag:** The tag `music_energy_100_near` is added to the boss, likely influencing in-game music based on its proximity to the player.

### Death (`death` function)

*   **Apparition Spawning:** Upon defeat, the boss spawns `apparition_spawn_fx.xml` entities at locations marked by `boss_phase2_marker` tags. This suggests a visual or gameplay effect related to the boss's demise.
*   **Persistent Flag:** The persistent flag `miniboss_sky` is added, likely for tracking game progression or unlocking content.
*   **Stats Logging:** Player kill statistics are logged for the defeated boss.

### Main Logic (`if EntityHasTag( GetUpdatedEntityID(), "boss" ) then ... else ... end`)

This section handles two distinct states for the `boss_sky` entity:

#### As the Main Boss (`EntityHasTag( GetUpdatedEntityID(), "boss" )`)

*   **Player Proximity Effects:** If the boss is within 350 units of the player:
    *   Removes the "PROTECTION_ALL" status effect from the player.
    *   Applies random water stains to the player's armor, making it less resistant.
*   **Circular Force Application:** Applies a circular force to the boss's position, likely for movement or visual effect.
*   **Vertical Teleportation:**
    *   If the boss's current Y-position exceeds its starting Y-position by more than 500 units, it triggers a teleportation sequence.
    *   This involves loading `teleportation_source.xml` and `teleportation_target.xml` particle effects.
    *   A teleportation sound effect is played.

#### As an Apparition (`else` block)

This block handles the behavior when the `boss_sky` entity is spawned as an apparition (e.g., by `apparition_spawn_fx.xml`).

*   **Apparition Spawning:** Spawns a new apparition entity using `SpawnApparition`.
*   **Player Health Sync (Apparition):** Similar to the main boss, the apparition's HP is synchronized with the player's HP.
*   **Boss Health Bar:** Adds a `BossHealthBarComponent` to the apparition, making it visible on the GUI within 350 units.
*   **Tagging:** The apparition is tagged as `miniboss` and `music_energy_000_near`.
*   **Music Energy Removal:** The `MusicEnergyAffectorComponent` is removed from the apparition, suggesting it doesn't influence music in the same way as the main boss.

## Key Components and Functions Used

*   `EntityGetTransform`: Retrieves the position of an entity.
*   `EntityGetFirstComponent`: Retrieves the first instance of a specific component from an entity.
*   `VariableStorageComponent`: Used to store and retrieve custom variables.
*   `DamageModelComponent`: Manages an entity's health and damage properties.
*   `ComponentSetValue2`: Sets a value for a component.
*   `ComponentGetValue2`: Gets a value from a component.
*   `EntityLoad`: Loads and spawns a new entity.
*   `EntityAddTag`: Adds a tag to an entity.
*   `EntityRemoveStainStatusEffect`: Removes a status effect from an entity.
*   `EntityAddRandomStains`: Applies random stains to an entity.
*   `VerletApplyCircularForce`: Applies a circular force to an entity.
*   `PhysicsBodyIDGetFromEntity`: Gets the physics body ID of an entity.
*   `GamePosToPhysicsPos`: Converts game coordinates to physics coordinates.
*   `PhysicsBodyIDSetTransform`: Sets the transform of a physics body.
*   `GamePlaySound`: Plays a sound effect.
*   `EntityHasTag`: Checks if an entity has a specific tag.
*   `get_players`: Returns a list of player entities.
*   `get_distance`: Calculates the distance between two points.
*   `AddFlagPersistent`: Adds a persistent flag to the game state.
*   `StatsLogPlayerKill`: Logs player kill statistics.
*   `SpawnApparition`: Spawns a new apparition entity.
*   `EntityAddComponent`: Adds a new component to an entity.
*   `EntityRemoveComponent`: Removes a component from an entity.
*   `CellFactory_GetType`: Retrieves the type of a cell (e.g., "water").