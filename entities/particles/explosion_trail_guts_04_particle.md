---
title: Explosion Trail Guts 04 Particle
category: entities/particles
---

---

# Explosion Trail Guts 04 Particle

This entity defines a particle effect used in explosions, specifically a "guts" trail. It inherits from a base explosion trail particle and customizes its appearance and behavior.

## Key Components

### Base Entity

*   **Inheritance:** `data/entities/particles/particle_explosion/explosion_trail_guts_01.xml`
    *   This indicates that `explosion_trail_guts_04.xml` builds upon the properties and behaviors defined in `explosion_trail_guts_01.xml`, likely modifying specific visual or physical aspects.

### PhysicsImageShapeComponent

*   **`image_file`**: `data/particles/guts_04.png`
    *   Specifies the visual sprite for this particle. This is the unique texture that makes this particle appear as "guts."
*   **`material`**: `bone`
    *   Defines the physical material properties of the particle. This influences how it interacts with the game world (e.g., collision, physics).

### LuaComponent

*   **`execute_every_n_frame`**: `5`
    *   This component introduces a staggered initialization behavior. The Lua script associated with this component will execute its logic every 5 frames.
    *   **Purpose:** The comment `<!-- staggered init so that guts stick less together -->` explains that this delay helps prevent multiple particles from spawning and sticking together immediately upon creation, leading to a more dispersed and natural-looking trail.