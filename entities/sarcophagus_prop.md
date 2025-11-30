---
title: Sarcophagus Prop
category: entities
---

# Sarcophagus Prop

This document describes the `sarcophagus.xml` entity, which represents a sarcophagus prop in Noita.

## Entity Definition

The sarcophagus is defined as a `prop` with the `pixelsprite` tag.

```xml
<Entity tags="prop,pixelsprite" >
	...
</Entity>
```

## Key Components

### PixelSpriteComponent

This component handles the visual representation and basic physics properties of the sarcophagus.

*   **`image_file`**: Specifies the sprite used for the sarcophagus.
    *   `data/props_gfx/sarcophagus.png`
*   **`anchor_x`**, **`anchor_y`**: Define the anchor point for the sprite.
    *   `anchor_x="7"`
    *   `anchor_y="28"`
*   **`create_box2d_bodies`**: Enables the creation of Box2D physics bodies for collision detection.
    *   `create_box2d_bodies="1"`
*   **`clean_overlapping_pixels`**: Ensures that overlapping pixels are handled correctly.
    *   `clean_overlapping_pixels="1"`
*   **`material`**: Sets the material type for physics interactions.
    *   `material="rock_loose"`

### SimplePhysicsComponent

This component governs basic physics behavior.

*   **`can_go_up`**: Determines if the object can move upwards.
    *   `can_go_up="0"` (Sarcophagus cannot move upwards)

### VelocityComponent

This component is present to allow for velocity to be applied, though it's not explicitly configured with values in this definition.

```xml
<VelocityComponent />
```