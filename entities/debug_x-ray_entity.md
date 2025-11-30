---
title: Debug X-Ray Entity
category: entities
---

# Debug X-Ray Entity

This entity provides a debug tool that allows players to see through walls and other obstacles.

## MagicXRayComponent

This component enables the X-ray vision effect.

### Key Attributes:

*   `radius`: The maximum distance the X-ray effect extends from the player.
*   `steps_per_frame`: The number of steps taken per frame to render the X-ray effect, influencing its smoothness and performance.

## LightComponent

This component adds a light source to the entity, illuminating the area around it.

### Key Attributes:

*   `_enabled`: Controls whether the light component is active.
*   `r`, `g`, `b`: The red, green, and blue components of the light's color.
*   `radius`: The radius of the light's illumination.