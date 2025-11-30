---
title: Neutralizer Target Entity
category: entities
---

# Neutralizer Target Entity

This entity represents a target that can be affected by the "Neutralizer" effect in Noita. When hit by a projectile with the Neutralizer effect, it applies a debuff.

## Key Components and Attributes

### Entity Tags

*   `neutralizer_target`: Identifies this entity as a potential target for the Neutralizer effect.

### InheritTransformComponent

This component is used to inherit transform properties, specifically the position.

*   `only_position="1"`: Indicates that only the position should be inherited, not rotation or scale.

### Transform

Defines the initial position of the entity in the game world.

*   `position.x="0"`: The X-coordinate of the entity's position.
*   `position.y="-8"`: The Y-coordinate of the entity's position.

### GameEffectComponent

Applies a game effect to the entity.

*   `effect="MOVEMENT_SLOWER_2X"`: The specific effect applied. In this case, it slows movement by 2 times.
*   `frames="-1"`: The duration of the effect. `-1` typically signifies an indefinite duration until removed or the entity is destroyed.

### SpriteComponent

Defines the visual representation of the entity.

*   `image_file="data/projectiles_gfx/target2.xml"`: The path to the sprite's image file.
*   `emissive="1"`: Makes the sprite emissive, meaning it will glow.

### LifetimeComponent

Determines how long the entity will exist before being removed.

*   `lifetime="600"`: The entity will last for 600 frames (approximately 10 seconds).