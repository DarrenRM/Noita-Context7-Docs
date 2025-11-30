---
title: Minecart Entity
category: entities
---

# Minecart Entity

This document describes the `minecart.xml` entity, which defines the behavior and appearance of a minecart in Noita. It utilizes several physics components to simulate its movement and interaction with the game world.

## Key Components

### `PhysicsBody2Component`

This component defines the main physics body for the minecart.

| Attribute          | Description                                                              |
| :----------------- | :----------------------------------------------------------------------- |
| `allow_sleep`      | Determines if the body can enter a sleep state when inactive.            |
| `linear_damping`   | Reduces linear velocity over time.                                       |
| `angular_damping`  | Reduces angular velocity over time.                                      |
| `kill_entity_after_initialized` | If set to 1, the entity will be destroyed immediately after its physics are initialized. This is likely a placeholder or for specific use cases. |

### `PhysicsImageShapeComponent`

This component defines the visual representation and collision shape of the minecart.

| Attribute   | Description