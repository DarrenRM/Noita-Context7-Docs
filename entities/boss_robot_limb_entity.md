---
title: Boss Robot Limb Entity
category: entities
---

# Boss Robot Limb Entity

This entity defines a single limb for the boss robot. It utilizes several components to manage its visual representation and movement behavior.

## Key Components

### `IKLimbWalkerComponent`

This component is essential for the limb's ability to participate in walking animations and movement. Specific parameters for this component are not detailed in the provided XML, but it's the core logic for limb locomotion.

### `IKLimbComponent`

This component defines the physical properties of the limb.

*   **`length`**: The length of the limb.
    *   **Value**: `160`

### `SpriteComponent`

This entity uses multiple `SpriteComponent`s to render the limb. Each `SpriteComponent` points to a different image file and defines its position and rendering properties.

*   **`image_file`**: Path to the sprite image.
*   **`offset_x`**: Horizontal offset for the sprite.
*   **`offset_y`**: Vertical offset for the sprite.
*   **`update_transform`**: Controls if the sprite's transform updates with the entity. Set to `0` (false) for these sprites.
*   **`update_transform_rotation`**: Controls if the sprite's rotation updates with the entity. Set to `0` (false) for these sprites.
*   **`z_index`**: Determines the rendering order of the sprite. Higher values are rendered on top.

#### Sprite Configurations:

| `image_file`                                    | `offset_x` | `offset_y` | `z_index` |
| :---------------------------------------------- | :--------- | :--------- | :-------- |
| `data/entities/animals/boss_robot/limb_1.png`   | `0`        | `4.5`      | `10`      |
| `data/entities/animals/boss_robot/limb_2.png`   | `0`        | `2.5`      | `10`      |
| `data/entities/animals/boss_robot/knee.png`     | `4.5`      | `4.5`      | `10`      |