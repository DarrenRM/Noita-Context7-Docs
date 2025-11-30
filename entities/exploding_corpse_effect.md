---
title: Exploding Corpse Effect
category: entities
---

# Exploding Corpse Effect

This entity defines a special effect that causes a corpse to explode after a certain duration.

## Key Components

### GameEffectComponent

This component governs the behavior of the game effect.

| Attribute           | Description                                                                                                |
| :------------------ | :--------------------------------------------------------------------------------------------------------- |
| `effect`            | Specifies the type of effect. Here, it's set to `EXPLODING_CORPSE`.                                        |
| `frames`            | The duration of the effect in frames (600 frames = 10 seconds at 60 FPS).                                  |
| `ragdoll_effect`    | Determines the effect applied to the ragdoll. `CUSTOM_RAGDOLL_ENTITY` indicates a custom entity is used. |
| `ragdoll_effect_custom_entity_file` | The file path to the custom entity that will be spawned as the ragdoll.                               |