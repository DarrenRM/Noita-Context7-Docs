---
title: Big Light Entity
category: entities
---

# Big Light Entity

This entity defines a large, white light source.

## LightComponent

This component controls the properties of the light emitted by the entity.

### Key Attributes:

*   `_enabled`: Controls whether the light component is active.
*   `r`, `g`, `b`: Define the red, green, and blue components of the light's color (0-255). In this case, it's pure white.
*   `radius`: The maximum distance the light will illuminate.

```xml
<Entity>
  
  <LightComponent 
    _enabled="1"
    r="255"
    g="255"
    b="255"
	radius="1000" >
  </LightComponent>
  
</Entity>
```