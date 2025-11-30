---
title: Spike Entity
category: entities
---

# Spike Entity

This document describes the `spike.xml` entity, which represents a spike trap in Noita.

## Core Components

### `CrawlerAnimalComponent`

This component defines the behavior of the spike. Despite its name, it's used here to control its static nature and interaction properties.

| Attribute              | Description                                                                 |
| :--------------------- | :-------------------------------------------------------------------------- |
| `animate`              | `0` indicates no animation.                                                 |
| `give_up_time`         | `999` suggests it never gives up, remaining active indefinitely.            |
| `gravity`              | `600` defines its gravitational pull.                                       |
| `attack_from_ceiling_check_ray_length` | `1` is a short ray length for ceiling checks.                           |
| `speed`                | `0` means the spike is stationary.                                          |
| `collision_damage`     | `0` indicates that the spike itself does not deal damage on collision.      |

### `SpriteComponent`

This component handles the visual representation of the spike.

| Attribute      | Description                                     |
| :------------- | :---------------------------------------------- |
| `image_file`   | `data/buildings_gfx/spike.xml` specifies the sprite's graphical asset. |
| `rect_animation` | `stand` indicates the default animation state.  |

### `MoveToSurfaceOnCreateComponent`

This component ensures the spike positions itself correctly upon creation.

| Attribute           | Description                                       |
| :------------------ | :------------------------------------------------ |
| `offset_from_surface` | `2` sets a small offset from the surface it attaches to. |

### `CameraBoundComponent`

This component manages the spike's visibility and behavior relative to the camera.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `max_count` | `900` is the maximum number of these entities that can exist simultaneously. |
| `distance`  | `160000` defines the maximum distance from the camera for the entity to be active. |