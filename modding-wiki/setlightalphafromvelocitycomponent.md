---
title: SetLightAlphaFromVelocityComponent
source: https://noita.wiki.gg/wiki/Documentation:SetLightAlphaFromVelocityComponent
category: modding-wiki
---

# SetLightAlphaFromVelocityComponent

This documentation page explains the `SetLightAlphaFromVelocityComponent` in Noita, a component that dynamically adjusts the alpha (transparency) of a light source based on its velocity. Understanding this component is crucial for modders who want to create dynamic visual effects for entities, such as making lights flicker or pulse when they move.

## Component Overview

The `SetLightAlphaFromVelocityComponent` allows you to link the intensity of a light emitted by an entity to its movement speed. This can be used to create a variety of visual effects, from subtle pulses to dramatic flares.

### Component XML Structure

The component is added to an entity's XML definition.

```xml
<SetLightAlphaFromVelocityComponent
    min_alpha="0.1"
    max_alpha="1.0"
    min_velocity="10"
    max_velocity="100"
    velocity_multiplier="1.0"
    >
</SetLightAlphaFromVelocityComponent>
```

### Component Properties

| Property              | Type    | Default | Description