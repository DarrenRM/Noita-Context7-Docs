---
title: Movement Slower Effect
category: entities
---

---

# Movement Slower Effect

This entity defines a game effect that slows down the movement of entities it is applied to.

## Key Components

### GameEffectComponent

This component is responsible for defining the specific game effect and its duration.

| Attribute | Description                                     |
| :-------- | :---------------------------------------------- |
| `effect`  | The type of effect to apply. `MOVEMENT_SLOWER` reduces movement speed. |
| `frames`  | The duration of the effect in game frames (60 frames = 1 second). |

## Example Usage

This entity is typically spawned by other game mechanics or spells to apply the slowing effect to a target. For instance, a spell might spawn this entity at the location of an enemy hit.