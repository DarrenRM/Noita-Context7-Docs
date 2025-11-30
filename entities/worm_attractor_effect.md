---
title: Worm Attractor Effect
category: entities
---

# Worm Attractor Effect

This entity defines a game effect that attracts worms.

## Key Components

### GameEffectComponent

This component governs the behavior and duration of the game effect.

| Attribute | Value | Description |
|---|---|---|
| `_tags` | `effect_worm,effect_worm_attractor` | Tags associated with this effect. |
| `effect` | `WORM_ATTRACTOR` | Specifies the type of effect, in this case, attracting worms. |
| `frames` | `600` | The duration of the effect in game frames (approximately 10 seconds). |