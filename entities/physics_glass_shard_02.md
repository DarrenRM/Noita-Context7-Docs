---
title: Physics Glass Shard 02
category: entities
---

# Physics Glass Shard 02

This entity defines a physics-enabled glass shard prop. It's a simple object designed to interact with the game's physics engine.

## Key Components

### Base Entity

*   **`Base file="data/entities/base_item_physics.xml"`**: Inherits core physics item functionalities.

### Physics Body Component

*   **`on_death_really_leave_body="1"`**: Ensures the physics body persists even after the entity is considered "dead" or removed from active gameplay, allowing it to remain in the world as a physical object.

### Physics Image Shape Component

*   **`centered="1"`**: Centers the sprite image on the entity's origin.
*   **`image_file="data/props_gfx/glass_shard_02.png"`**: Specifies the visual sprite for the glass shard.
*   **`material="glass_box2d"`**: Assigns a physics material, likely defining its collision properties and behavior within the Box2D physics engine.

### Lifetime Component

*   **`lifetime="360"`**: Sets the duration (in frames) for which this entity will exist before being removed from the game.