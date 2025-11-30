---
title: Underground Sampo Ending Spot
category: entities
---

# Underground Sampo Ending Spot

This entity represents a specific location within the game world, likely tied to an ending sequence involving the "Sampo."

## Entity Definition

```xml
<Entity tags="ending_sampo_spot_underground">
<!-- empty entities don't get serialized -->
<SpriteComponent image_file="data/debug/empty.png" />
</Entity>
```

## Key Components

*   **`tags`**: `ending_sampo_spot_underground` - This tag is crucial for identifying and referencing this specific entity within the game's logic and potentially for triggering events related to the Sampo ending.
*   **`SpriteComponent`**:
    *   `image_file`: `data/debug/empty.png` - This indicates that the entity itself does not have a visible sprite. It's likely a placeholder or a purely functional entity used for its tag and position.

## Purpose

This entity serves as a marker or trigger point for a specific game ending. Its lack of visual components suggests it's not meant to be directly interacted with by the player but rather to be detected by game logic.