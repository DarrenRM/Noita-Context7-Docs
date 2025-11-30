---
title: Rainbow Farts Effect
category: entities
---

# Rainbow Farts Effect

This entity defines the visual and gameplay effect of "Rainbow Farts" in Noita. It primarily utilizes a `GameEffectComponent` to trigger the effect and a `ParticleEmitterComponent` to generate the visual particles.

## Key Components

### GameEffectComponent

This component is responsible for applying the core "RAINBOW_FARTS" effect.

| Attribute | Description                                    |
| :-------- | :--------------------------------------------- |
| `effect`  | The specific game effect to apply (RAINBOW_FARTS). |
| `frames`  | Duration of the effect in frames (600 frames). |

### ParticleEmitterComponent

This component dictates how the visual "fart" particles are generated and behave.

| Attribute               | Description