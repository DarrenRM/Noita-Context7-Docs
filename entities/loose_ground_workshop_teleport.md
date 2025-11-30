---
title: Loose Ground Workshop Teleport
category: entities
---

# Loose Ground Workshop Teleport

This entity defines a loose ground object that can trigger a teleportation effect, likely used in a workshop or testing environment.

## Entity Components

### LooseGroundComponent

This component governs the behavior of the loose ground.

| Attribute      | Description                                                                 |
|----------------|-----------------------------------------------------------------------------|
| `probability`  | The chance (0.0 to 1.0) that this loose ground will spawn or activate.      |
| `max_distance` | The maximum distance from the player at which this loose ground can be active. |

### LifetimeComponent

This component controls how long the entity persists.

| Attribute             | Description                                                                                             |
|-----------------------|---------------------------------------------------------------------------------------------------------|
| `lifetime`            | The base duration (in frames) the entity will exist.                                                    |
| `randomize_lifetime.min` | The minimum amount to subtract from the base `lifetime` for randomization.                              |
| `randomize_lifetime.max` | The maximum amount to add to the base `lifetime` for randomization.                                     |