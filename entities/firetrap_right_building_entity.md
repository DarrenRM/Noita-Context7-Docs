---
title: Firetrap (Right) Building Entity
category: entities
---

# Firetrap (Right) Building Entity

This document describes the `firetrap_right.xml` entity, which represents a right-facing firetrap building in Noita. It inherits its base functionality from `firetrap_left.xml` and adds specific visual and functional components.

## Key Components

### Base Entity (`<Base>`)

This element inherits properties from `firetrap_left.xml`, providing the fundamental structure and behavior of the firetrap.

*   **`file="data/entities/buildings/firetrap_left.xml"`**: Specifies the parent entity file from which this entity inherits.

### Sprite Component (`<SpriteComponent>`)

Defines the visual appearance of the firetrap.

*   **`image_file="data/buildings_gfx/firetrap_right.xml"`**: Points to the graphical asset file used for rendering the right-facing firetrap.

### Hitbox Component (`<HitboxComponent>`)

Determines the collision area of the firetrap.

*   **`_enabled="1"`**: Enables the hitbox.
*   **`aabb_min_x="-5"`**: Minimum X-axis coordinate of the Axis-Aligned Bounding Box (AABB).
*   **`aabb_max_x="0"`**: Maximum X-axis coordinate of the AABB.
*   **`aabb_min_y="-5"`**: Minimum Y-axis coordinate of the AABB.
*   **`aabb_max_y="5"`**: Maximum Y-axis coordinate of the AABB.

### Pixel Scene Component (`<PixelSceneComponent>`)

Defines a visual overlay or interaction layer for the firetrap.

*   **`pixel_scene="data/biome_impl/crypt/trap_frame_right.png"`**: Specifies the pixel scene file, likely a graphical element that frames the trap.
*   **`offset_x="-15"`**: X-axis offset for the pixel scene.
*   **`offset_y="-10"`**: Y-axis offset for the pixel scene.

### Game Effect Components (`<GameEffectComponent>`)

These nested entities apply specific game effects to entities that interact with the firetrap.

#### Stun Protection (Freeze)

*   **`effect="STUN_PROTECTION_FREEZE"`**: Grants immunity to freezing effects.
*   **`frames="-1"`**: Indicates the effect is permanent as long as the entity is within the trap's influence.

#### Stun Protection (Electricity)

*   **`effect="STUN_PROTECTION_ELECTRICITY"`**: Grants immunity to electricity effects.
*   **`frames="-1"`**: Indicates the effect is permanent as long as the entity is within the trap's influence.

## Summary

The `firetrap_right.xml` entity is a specialized version of the firetrap, designed to be placed on the right side. It uses a specific sprite and hitbox configuration. Crucially, it provides temporary immunity to both freezing and electrical stun effects for any entities that come into contact with it, likely as a defensive mechanism within its environment.