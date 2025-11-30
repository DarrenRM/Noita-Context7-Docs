---
title: Radioactive Allergy Effect
category: entities
---

# Radioactive Allergy Effect

This entity defines a game effect that applies a "Radioactive Allergy" to the player.

## Key Components

### GameEffectComponent
This component is responsible for applying the game effect.

*   **`effect`**: Specifies the type of effect. In this case, it's `ALLERGY_RADIOACTIVE`.
*   **`frames`**: The duration of the effect in frames. Here, it's set to `600` frames (approximately 10 seconds).

## Usage

This entity is likely used to trigger a temporary debuff on the player when certain conditions are met, such as interacting with radioactive materials or environments. The `ALLERGY_RADIOACTIVE` effect would then apply its associated gameplay mechanics (e.g., damage over time, visual distortions) for the specified duration.