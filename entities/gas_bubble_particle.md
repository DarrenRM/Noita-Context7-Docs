---
title: Gas Bubble Particle
category: entities
---

---

# Gas Bubble Particle

This document describes the `gas_bubble.xml` entity, which defines the behavior and appearance of gas bubbles in Noita.

## Entity Definition

The `gas_bubble.xml` entity is a simple particle effect.

```xml
<Entity>
    <!-- Sprite component for visual representation -->
    <SpriteComponent 
        alpha="1" 
        z_index="-2"
        image_file="data/particles/gas_bubble_0$[1-3].xml" >
    </SpriteComponent>

    <!-- GasBubble component for physics and movement -->
    <GasBubbleComponent
    	max_speed="90"
    	acceleration="-200">
    </GasBubbleComponent>
  
</Entity>
```

## Key Components and Attributes

### SpriteComponent

This component handles the visual aspects of the gas bubble.

*   **`alpha`**: Controls the transparency of the bubble (1 is fully opaque).
*   **`z_index`**: Determines the drawing order. A negative value places it behind other elements.
*   **`image_file`**: Specifies the image(s) to be used for the bubble. The `$[1-3]` indicates that it will randomly pick one of `gas_bubble_01.xml`, `gas_bubble_02.xml`, or `gas_bubble_03.xml` for its appearance.

### GasBubbleComponent

This component defines the physics and movement characteristics of the gas bubble.

*   **`max_speed`**: The maximum velocity the bubble can reach.
*   **`acceleration`**: The rate at which the bubble's speed changes. A negative value indicates deceleration or upward movement against gravity.