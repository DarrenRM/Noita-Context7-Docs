---
title: Tiny Dark Lukki Limb (Animated)
category: entities
---

# Tiny Dark Lukki Limb (Animated)

This entity defines a small, animated limb for the "dark lukki" creature in Noita. It's designed to be part of a larger animated entity, likely a leg or appendage.

## Key Components

### InheritTransformComponent

This component is standard for entities that need to inherit transformations (position, rotation, scale) from their parent or the world.

*   `_tags`: `enabled_in_world`, `enabled_in_hand` - Indicates the entity is active in the game world and can be held.

### IKLimbComponent

This component is crucial for inverse kinematics (IK) limb behavior, allowing for more natural animation and movement.

*   `_tags`: `enabled_in_world`, `enabled_in_hand`
*   `length`: `12` - Defines the length of the limb segment.

### SpriteComponent (x2)

This entity uses two identical `SpriteComponent` instances. This is likely for animation purposes, where each sprite might represent a different frame or state of the limb.

*   `_tags`: `enabled_in_world`, `enabled_in_hand`
*   `image_file`: `data/entities/animals/lukki/lukki_feet/lukki_limb_tiny_dark.png` - Specifies the image file used for the sprite.
*   `z_index`: `1.1` - Controls the drawing order of the sprite. Higher values are drawn on top.
*   `offset_x`: `0` - Horizontal offset of the sprite.
*   `offset_y`: `1` - Vertical offset of the sprite.
*   `update_transform`: `0` - Disables automatic transform updates for this sprite.
*   `update_transform_rotation`: `0` - Disables automatic rotation updates for this sprite.