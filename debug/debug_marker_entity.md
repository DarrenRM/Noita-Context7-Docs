---
title: Debug Marker Entity
category: guides
---

<Entity >
   
  <SpriteComponent 
    _enabled="1" 
    alpha="1" 
    offset_x="0"
    offset_y="0"
    image_file="data/debug/box_10x10.png" 
    z_index="-2.5"
     >
  </SpriteComponent>
  
</Entity>
```

---
title: Debug Marker Entity
category: entities
---

# Debug Marker Entity

This entity is a simple visual marker used for debugging purposes within Noita. It primarily utilizes a `SpriteComponent` to display a visual representation.

## Key Components

### SpriteComponent

This component defines the visual appearance of the debug marker.

*   **`_enabled`**: (1) Indicates that the sprite component is active.
*   **`alpha`**: (1) Sets the opacity of the sprite to fully opaque.
*   **`offset_x`**: (0) No horizontal offset for the sprite.
*   **`offset_y`**: (0) No vertical offset for the sprite.
*   **`image_file`**: `data/debug/box_10x10.png` - Specifies the image file used for the sprite. This is a 10x10 pixel box image from the debug assets.
*   **`z_index`**: (-2.5) Determines the rendering order. A negative value places it behind most other game elements.