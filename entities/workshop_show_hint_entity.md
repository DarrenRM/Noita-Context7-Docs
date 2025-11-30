---
title: Workshop Show Hint Entity
category: entities
---

# Workshop Show Hint Entity

This entity defines a visual hint element within the Noita workshop. It's primarily used to display information or prompts to the player.

## Key Components

### HitboxComponent
This component defines the physical boundaries of the hint element.

*   **aabb_min_x**: Minimum X-axis coordinate of the bounding box.
*   **aabb_min_y**: Minimum Y-axis coordinate of the bounding box.
*   **aabb_max_x**: Maximum X-axis coordinate of the bounding box.
*   **aabb_max_y**: Maximum Y-axis coordinate of the bounding box.

```xml
<HitboxComponent 
  aabb_min_x="-64" 
  aabb_min_y="-48"
  aabb_max_x="64" 
  aabb_max_y="48" >
</HitboxComponent>
```