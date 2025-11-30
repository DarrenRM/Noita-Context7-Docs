---
title: Explosion Trail Guts Particle
category: entities/particles
---

---

# Explosion Trail Guts Particle

This document describes the configuration for a particle entity used in Noita, specifically for an explosion trail effect involving "guts."

## Entity Configuration

The particle is defined as an `Entity` with the following key components:

### PhysicsBody2Component

This component indicates that the entity has physics properties. No specific attributes are detailed in the provided snippet, implying default physics behavior.

### PhysicsImageShapeComponent

This component defines the visual representation and physical shape of the particle.

*   **`image_file`**: `data/particles/guts_01.png` - Specifies the texture file used for the particle's appearance.
*   **`use_sprite`**: `1` - Indicates that the image should be treated as a sprite.
*   **`centered`**: `1` - Centers the sprite on the particle's origin.
*   **`is_root`**: `1` - Marks this as the root visual element of the entity.
*   **`material`**: `meat` - Assigns a material property, likely influencing its interaction with other game elements.

### LuaComponent

This component attaches a Lua script to the entity, controlling its behavior.

*   **`script_source_file`**: `data/scripts/particles/guts_init.lua` - The path to the Lua script that initializes and manages the particle's logic.
*   **`execute_every_n_frame`**: `3` - The script will execute its logic every 3 frames.
*   **`remove_after_executed`**: `1` - The Lua script will be removed from the entity after its first execution.