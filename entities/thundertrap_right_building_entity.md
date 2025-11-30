---
title: Thundertrap Right Building Entity
category: entities
---

# Thundertrap Right Building Entity

This document describes the `thundertrap_right.xml` entity, which represents the right-hand side of a thundertrap building in Noita. It inherits its base functionality from `thundertrap_left.xml` and adds specific visual and functional components.

## Key Components

### Base Entity Inheritance

*   **`Base file="data/entities/buildings/thundertrap_left.xml"`**: This indicates that `thundertrap_right.xml` inherits all properties and components from `thundertrap_left.xml`. Modifications or additions here will be layered on top of the base entity.

### Sprite Component

*   **`SpriteComponent image_file="data/buildings_gfx/thundertrap_right.xml"`**: Defines the visual appearance of the thundertrap's right side. This points to a separate XML file that likely contains sprite definitions for the building's graphics.

### Hitbox Component

*   **`HitboxComponent _enabled="1"`**: Enables the hitbox for this entity.
*   **`aabb_min_x="-5"`, `aabb_max_x="0"`**: Defines the horizontal bounds of the hitbox.
*   **`aabb_min_y="-5"`, `aabb_max_y="5"`**: Defines the vertical bounds of the hitbox. This component determines how the entity interacts with physics and other game elements.

### Pixel Scene Component

*   **`PixelSceneComponent pixel_scene="data/biome_impl/crypt/trap_frame_right.png"`**: This component allows for the rendering of a pixel-based scene, likely used for detailed visual elements or collision masks within the building's structure.
*   **`offset_x="-15"`, `offset_y="-10"`**: Specifies the offset of the pixel scene relative to the entity's origin.

### Game Effect Components

This entity has two distinct child entities, each with a `GameEffectComponent` to grant passive buffs to entities within their vicinity.

#### Entity 1: Freeze Protection

*   **`InheritTransformComponent`**: Ensures this effect entity inherits the transform (position, rotation, scale) of its parent.
*   **`GameEffectComponent effect="STUN_PROTECTION_FREEZE" frames="-1"`**: Grants immunity to freezing effects. `frames="-1"` indicates the effect is permanent as long as the entity is active.

#### Entity 2: Electricity Protection

*   **`InheritTransformComponent`**: Ensures this effect entity inherits the transform of its parent.
*   **`GameEffectComponent effect="PROTECTION_ELECTRICITY" frames="-1"`**: Grants immunity to electricity damage and effects. `frames="-1"` indicates the effect is permanent.

## Summary

The `thundertrap_right.xml` entity serves as the right-hand counterpart to the `thundertrap_left.xml` entity. It primarily defines its visual representation and hitbox. Crucially, it also incorporates two passive game effects: protection against freezing and electricity, making it a defensive structure when paired with its left counterpart.