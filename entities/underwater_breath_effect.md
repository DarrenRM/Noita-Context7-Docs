---
title: Underwater Breath Effect
category: entities
---

# Underwater Breath Effect

This entity defines the game effect that allows a player to breathe underwater.

## Key Components

### GameEffectComponent

This component is responsible for applying the actual game effect.

| Attribute      | Description                                                                 |
|----------------|-----------------------------------------------------------------------------|
| `effect`       | Specifies the type of effect to apply. `BREATH_UNDERWATER` enables underwater breathing. |
| `frames`       | The duration of the effect in frames. `-1` indicates a permanent effect (until removed by other means). |
| `exclusivity_group` | Groups effects that cannot be active simultaneously. `0` means this effect has no exclusivity conflicts with other effects in group 0. |