---
title: CardinalMovementComponent
source: https://noita.wiki.gg/wiki/Documentation:CardinalMovementComponent
category: modding-wiki
---

# CardinalMovementComponent

This documentation page details the `CardinalMovementComponent` in Noita, a crucial component for defining how entities move in cardinal directions. Understanding and modifying this component is essential for modders looking to alter character movement, enemy AI, or the behavior of various in-game objects.

## Overview

The `CardinalMovementComponent` is responsible for controlling an entity's movement along the X and Y axes. It dictates how an entity responds to directional inputs, its movement speed, and other related kinematic properties. Modifying this component allows for fine-grained control over how entities navigate the game world.

## Component Properties

The `CardinalMovementComponent` has several properties that can be adjusted within the `data/components/` directory. These properties are typically defined in XML files.

### Movement Speed

This property controls the base speed at which the entity moves.

| Property Name | Type   | Description                               | Default Value |
| :------------ | :----- | :---------------------------------------- | :------------ |
| `max_speed`   | float  | The maximum speed the entity can reach.   | `100`         |

### Acceleration and Deceleration

These properties define how quickly the entity reaches its maximum speed and how quickly it stops.

| Property Name | Type   | Description                                       | Default Value |
| :------------ | :----- | :------------------------------------------------ | :------------ |
| `acceleration` | float  | The rate at which speed increases.                | `1000`        |
| `friction`    | float  | The rate at which speed decreases when no input. | `1000`        |

### Jump Properties

This component also handles jumping behavior.

| Property Name | Type   | Description