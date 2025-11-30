---
title: Polymorph Cessation Effect
category: entities
---

# Polymorph Cessation Effect

This entity defines a game effect that stops polymorph transformations.

## GameEffectComponent

This is the primary component responsible for the effect's behavior.

### Key Attributes:

*   **`effect`**: Specifies the type of game effect. In this case, it's `POLYMORPH_CESSATION`, indicating the cessation of polymorphing.
*   **`frames`**: Determines the duration of the effect in game frames. A value of `20` means the effect lasts for 20 frames.
*   **`disable_movement`**: A flag to control whether movement is disabled during the effect. `0` means movement is *not* disabled.
*   **`polymorph_target`**: The XML path to the entity that the polymorph transformation will be reverted to or prevented from occurring. Here, it's set to `data/entities/animals/nibbana.xml`.