---
title: Spruce Tree 2 Entity
category: entities
---

# Spruce Tree 2 Entity

This document describes the `tree_spruce_2.xml` entity, representing a spruce tree in Noita. It focuses on key components and attributes relevant for AI-assisted modding.

## Entity Definition

The root element defines the entity with basic properties.

```xml
<Entity
  name="unknown"
  tags="vegetation,pixelsprite" >
  <!-- ... components ... -->
</Entity>
```

*   **`name`**: "unknown" - This is a placeholder and might be intended to be dynamically set or is a default.
*   **`tags`**: `vegetation`, `pixelsprite` - These tags categorize the entity, indicating it's a plant and uses pixel art.

## Components

### PixelSpriteComponent

This component handles the visual representation of the tree.

```xml
<PixelSpriteComponent
  _enabled="1"
  image_file="data/vegetation/tree_spruce_2.png"
  anchor_x="35"
  anchor_y="132"
  clean_overlapping_pixels="0"
>
</PixelSpriteComponent>
```

*   **`_enabled`**: `1` - The component is active.
*   **`image_file`**: `data/vegetation/tree_spruce_2.png` - Specifies the sprite image used for this tree.
*   **`anchor_x`**: `35` - The horizontal anchor point for the sprite.
*   **`anchor_y`**: `132` - The vertical anchor point for the sprite.
*   **`clean_overlapping_pixels`**: `0` - Disables the cleaning of overlapping pixels, which can affect how the sprite is rendered.

### SimplePhysicsComponent

This component defines basic physics properties.

```xml
<SimplePhysicsComponent
  can_go_up="0"
>
</SimplePhysicsComponent>
```

*   **`can_go_up`**: `0` - The entity cannot move upwards. This is typical for static environmental objects.

### VelocityComponent

This component is present but empty, suggesting it might be a placeholder or intended for potential future use where velocity might be applied.

```xml
<VelocityComponent />
```