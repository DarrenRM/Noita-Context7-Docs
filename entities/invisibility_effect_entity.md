---
title: Invisibility Effect Entity
category: entities
---

# Invisibility Effect Entity

This entity defines the properties for an invisibility effect in Noita, primarily used for game mechanics and visual/audio feedback.

## Key Components

### GameEffectComponent

This component dictates the core behavior of the game effect.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `effect`  | Specifies the type of effect. Set to `INVISIBILITY`. |
| `frames`  | The duration of the effect in game frames (7200 frames ≈ 2 minutes). |

### AudioComponent

These components handle the sound effects associated with the invisibility.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `file`      | The audio bank file containing the sound events.                         |
| `event_root`| The root name for the audio event. Two are present: `game_effect/invisibility` and `game_effect/electrocution`. |

## Inheritance

### InheritTransformComponent

This component indicates that the entity inherits its transform properties (position, rotation, scale) from its parent or the context in which it's spawned. It has no specific configurable attributes in this definition.