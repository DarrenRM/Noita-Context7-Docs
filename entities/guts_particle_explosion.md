---
title: Guts Particle Explosion
category: entities
---

# Guts Particle Explosion

This entity defines the visual and physical properties of the "guts" particle effect, typically seen during explosions in Noita. It utilizes a Lua script for initialization and defines its physical shape and material.

## Key Components

### PhysicsBody2Component
This component enables the entity to participate in the physics simulation.

*   `update_entity_transform`: `1` - Ensures the entity's transform (position, rotation) is updated by the physics engine.

### PhysicsImageShapeComponent
Defines the physical shape of the particle using an image file.

*   `image_file`: `"data/particles/guts_01.png"` - Specifies the image used for the particle's shape.
*   `use_sprite`: `1` - Indicates that the `image_file` should be treated as a sprite.
*   `centered`: `1` - Centers the sprite on the entity's origin.
*   `is_root`: `1` - Marks this as the root shape component.
*   `material`: `"meat"` - Assigns the "meat" material to this particle, influencing its interactions.

### LuaComponent
This component executes a Lua script to initialize and manage the particle's behavior.

*   `script_source_file`: `"data/scripts/particles/guts_init.lua"` - The path to the Lua script responsible for the particle's logic.
*   `execute_every_n_frame`: `1` - The script will execute every frame.
*   `remove_after_executed`: `1` - The Lua component will be removed after its first execution.

## Ignored/Commented Components

The following components were present in the source but commented out. They might represent alternative or older implementations.

*   `VelocityComponent` (multiple instances): These define gravity and air friction, suggesting different velocity behaviors.
*   `SetStartVelocityComponent`: Used to randomize the initial speed and angle of particles.
*   `SimplePhysicsComponent`: A simpler physics component.
*   `SpriteComponent`: Defines the visual appearance of the particle, including the image file and alpha.
*   `ParticleEmitterComponent`: This component is typically used to spawn other particles, but it's commented out here, implying the "guts" particle itself is the primary effect, not an emitter.
*   `LifetimeComponent`: Defines the duration a particle exists, with randomization.