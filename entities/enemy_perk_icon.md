---
title: Enemy Perk Icon
category: entities
---

---

# Enemy Perk Icon

This entity defines the visual representation of a perk icon that appears when an enemy is affected by a perk.

## Key Components

### SpriteComponent
This component handles the visual display of the icon.

*   **`image_file`**: Specifies the texture file for the perk icon.
    *   Example: `"data/ui_gfx/perk_icons/extra_perk.png"`
*   **`offset_x`**: Horizontal offset for the sprite.
*   **`offset_y`**: Vertical offset for the sprite.
*   **`has_special_scale`**: Indicates if the sprite uses a special scaling method.

### InheritTransformComponent
This component allows the icon's transform to inherit from its parent, ensuring it's positioned correctly relative to the perk it represents.

*   **`use_root_parent`**: If set to `1`, it inherits transform from the root parent.
*   **`_tags`**: Tags that enable this component, such as `"enabled_in_hand"`.

#### Transform
Defines the position of the icon relative to its parent.

*   **`position.x`**: X-coordinate.
*   **`position.y`**: Y-coordinate.