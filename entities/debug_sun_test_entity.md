---
title: Debug Sun Test Entity
category: entities
---

# Debug Sun Test Entity

This entity is a debug tool designed to represent a "sun" effect, primarily for testing visual and particle emission components. It's based on `base_item_projectile.xml` and includes physics, sprite rendering, and particle emitters.

## Key Components

### Base Entity

*   **`Base file="data/entities/base_item_projectile.xml"`**: Inherits fundamental properties from a projectile base, suggesting it can be interacted with physically.

### Physics Components

*   **`PhysicsBodyComponent`**:
    *   `uid="1"`: Unique identifier.
    *   `allow_sleep="1"`: Allows the physics body to go to sleep when inactive.
    *   `fixed_rotation="0"`: Allows rotation.
    *   `auto_clean="0"`: Prevents automatic removal.
    *   `on_death_leave_physics_body="1"`: Ensures physics body persists after death.
*   **`PhysicsShapeComponent`**:
    *   `is_circle="1"`: Defines the physics shape as a circle.
    *   `radius_x="64"`, `radius_y="64"`: Sets the radius of the circular shape.
*   **`VelocityComponent`**: Standard component for velocity.

### Sprite Components

This entity uses two `SpriteComponent`s to achieve its visual effect:

1.  **Fog of War Hole Sprite**:
    *   `image_file="data/particles/fog_of_war_hole_huge.png"`: Uses a large hole image, likely to create a glowing or obscuring effect.
    *   `fog_of_war_hole="1"`: Specifically marks this sprite as a fog of war hole.
    *   `offset_x="98"`, `offset_y="98"`: Positions the sprite.
2.  **Sun Sprite**:
    *   `image_file="data/props_gfx/sun.png"`: Uses the actual "sun" graphic.
    *   `emissive="1"`: Makes the sprite emit light.
    *   `additive="1"`: Uses additive blending for a brighter, glowing effect.
    *   `offset_x="70"`, `offset_y="70"`: Positions the sprite.

### UI Component

*   **`UIInfoComponent`**:
    *   `name="$item_seed_d"`: Assigns a name, likely for debugging or internal identification.

### Particle Emitters

The entity features two identical `ParticleEmitterComponent`s, each responsible for emitting cosmetic particles to simulate a sun-like glow or energy.

*   **`ParticleEmitterComponent` (x2)**:
    *   `emitted_material_name`: Specifies the material of the emitted particles (`spark_yellow` and `spark`).
    *   `fade_based_on_lifetime="1"`: Particles fade out as their lifetime ends.
    *   `x_vel_min/max`, `y_vel_min/max`: Defines the velocity range for emitted particles.
    *   `area_circle_radius.min/max`: Sets the emission area to a circle.
    *   `velocity_always_away_from_center="100"`: Particles are pushed away from the emitter's center.
    *   `gravity.y="0"`: No gravity applied to particles.
    *   `friction="0.1"`: Applies friction to particles.
    *   `airflow_force`, `airflow_time`, `airflow_scale`: Parameters for airflow influence.
    *   `count_min/max`: Number of particles emitted per burst.
    *   `lifetime_min/max`: Duration particles exist.
    *   `create_real_particles="0"`: Only cosmetic particles are created.
    *   `emit_cosmetic_particles="1"`: Enables cosmetic particle emission.
    *   `draw_as_long="1"`: Particles are drawn as trails.
    *   `collide_with_grid="0"`: Particles do not collide with the grid.
    *   `render_on_grid="1"`: Particles are rendered on the grid.
    *   `emission_interval_min/max_frames="1"`: Particles are emitted every frame.
    *   `is_emitting="1"`: The emitter is active.