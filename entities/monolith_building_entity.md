---
title: Monolith Building Entity
category: entities
---

# Monolith Building Entity

This document describes the `monolith.xml` entity, which represents a building element in Noita.

## Entity Definition

The `Entity` tag defines the core properties of the monolith.

### Key Attributes:

*   **name**: `unknown` - The internal name for this entity.
*   **tags**: `building, house` - Categorizes the entity for game logic and modding.

## Components

The monolith entity utilizes several components to define its behavior and appearance.

### SpriteComponent

This component handles the visual representation of the monolith.

#### Key Attributes:

*   **image\_file**: `data/vegetation/monolith.png` - Specifies the texture file used for the sprite.
*   **offset\_x**: `10` - Horizontal offset for the sprite's position.
*   **offset\_y**: `47` - Vertical offset for the sprite's position.

### VelocityComponent

This component is present but empty, suggesting it might be a placeholder or intended for future use.

### SimplePhysicsComponent

This component is also present but empty, indicating that the monolith does not have complex physics interactions by default.