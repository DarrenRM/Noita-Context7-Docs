---
title: Spruce Tree 4 Entity
category: entities
---

# Spruce Tree 4 Entity

This document describes the `tree_spruce_4.xml` entity, representing a spruce tree in Noita. It focuses on key attributes relevant for AI-assisted modding.

## Entity Definition

The root element defines the entity with basic properties.

```xml
<Entity
  name="unknown"
  tags="vegetation,pixelsprite" >
  ...
</Entity>
```

*   **`name`**: "unknown" - This is a placeholder and can be customized for modded entities.
*   **`tags`**: "vegetation,pixelsprite" - These tags categorize the entity, indicating it's a plant and uses pixel art.

## PixelSpriteComponent

This component handles the visual representation of the tree.

```xml
<PixelSpriteComponent
  _enabled="1"
  image_file="data/vegetation/tree_spruce_4.png"
  anchor_x="35"
  anchor_y="132"
  clean_overlapping_pixels="0" >
  ...
</PixelSpriteComponent>
```

*   **`_enabled`**: "1" - Indicates the component is active.
*   **`image_file`**: "data/vegetation/tree_spruce_4.png" - Specifies the sprite image used for this tree.
*   **`anchor_x`**: "35" - The horizontal anchor point for the sprite.
*   **`anchor_y`**: "132" - The vertical anchor point for the sprite.
*   **`clean_overlapping_pixels`**: "0" - Controls how overlapping pixels are handled. "0" means no cleaning.

## SimplePhysicsComponent

This component defines basic physics properties.

```xml
<SimplePhysicsComponent
  can_go_up="0" >
  ...
</SimplePhysicsComponent >
```

*   **`can_go_up`**: "0" - Prevents the entity from moving upwards.

## VelocityComponent

This component is present but has no specific attributes defined, implying default velocity behavior.

```xml
<VelocityComponent />
```