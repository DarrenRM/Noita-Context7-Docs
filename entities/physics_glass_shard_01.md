---
title: Physics Glass Shard 01
category: entities
---

# Physics Glass Shard 01

This entity defines a breakable glass shard that behaves according to physics. It's a common prop that can be shattered and interact with the game world.

## Key Attributes

*   **`mortal` tag**: Indicates that this entity can be destroyed or die.
*   **`Base file="data/entities/base_item_physics.xml"`**: Inherits core physics-based item properties.
*   **`PhysicsBodyComponent`**:
    *   `on_death_really_leave_body="1"`: Ensures the physics body persists even after the entity is considered "dead" or removed, allowing for continued physical interaction.
*   **`PhysicsImageShapeComponent`**:
    *   `centered="1"`: Centers the image on the entity's origin.
    *   `image_file="data/props_gfx/glass_shard_01.png"`: Specifies the visual sprite for the shard.
    *   `material="glass_box2d"`: Defines the physical material properties, likely influencing its fragility and interaction with other physics objects.
*   **`LifetimeComponent`**:
    *   `lifetime="360"`: Sets the duration in frames (approximately 6 seconds) before the shard is automatically removed from the game.

## XML Structure

```xml
<Entity tags="mortal" >

  <Base file="data/entities/base_item_physics.xml" >
    <PhysicsBodyComponent
      on_death_really_leave_body="1"
    ></PhysicsBodyComponent>

    <PhysicsImageShapeComponent
      centered="1" 
      image_file="data/props_gfx/glass_shard_01.png"
      material="glass_box2d" >
    </PhysicsImageShapeComponent>
  </Base>

  <LifetimeComponent
      lifetime="360"
  ></LifetimeComponent>

</Entity>
```