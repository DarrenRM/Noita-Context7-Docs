---
title: Exploding Deer Projectile
category: entities
---

# Exploding Deer Projectile

This entity defines a projectile that behaves like a helpless deer, capable of escaping and exploding upon collision or after a set duration.

## Key Components

### Base Components

*   **`Base file="data/entities/base_projectile.xml"`**: Inherits fundamental projectile properties.
*   **`Base file="data/entities/base_helpless_animal.xml"`**: Inherits properties related to animal AI and behavior.

### AnimalAIComponent

This component governs the deer's AI behavior.

*   **`preferred_job="Escaping"`**: The deer's primary AI directive is to escape.
*   **`sense_creatures="1"`**: The deer can detect other creatures.
*   **`creature_detection_range_x="128"`**, **`creature_detection_range_y="160"`**: Defines the detection radius for creatures.
*   **`can_fly="0"`**: The deer cannot fly.

### DamageModelComponent

Handles damage and health properties.

*   **`hp="0.8"`**: The deer has very low health.
*   **`fire_probability_of_ignition="0.05"`**: A small chance of igniting.

### SpriteComponent

Defines the visual representation of the deer.

*   **`image_file="data/enemies_gfx/deer.xml"`**: Specifies the sprite sheet for the deer.
*   **`rect_animation="stand"`**: Sets the default animation to "stand".
*   **`offset_x="15"`**, **`offset_y="25"`**: Adjusts the sprite's position.

### CharacterPlatformingComponent

Controls movement and physics.

*   **`run_velocity="30"`**: The deer's running speed.
*   **`jump_velocity_y="-12"`**: The deer's jump strength.

### HitboxComponent

Defines the collision area of the deer.

*   **`aabb_min_x="-6.5"`**, **`aabb_max_x="6.5"`**: Horizontal bounds of the hitbox.
*   **`aabb_min_y="-10"`**, **`aabb_max_y="3"`**: Vertical bounds of the hitbox.

### ProjectileComponent

Defines the projectile's launch and flight characteristics.

*   **`speed_min="250"`**, **`speed_max="280"`**: The projectile's speed range.
*   **`bounces_left="4"`**: The projectile can bounce up to 4 times.
*   **`camera_shake_when_shot="5.0"`**: Triggers camera shake when the projectile is fired.
*   **`damage="0"`**: The projectile itself does no direct damage.
*   **`lifetime="-1"`**: The projectile does not expire on its own.

### CollisionTriggerComponent

Manages collision detection and triggers events.

*   **`timer_for_destruction="30"`**: The projectile will be destroyed after 30 frames if it collides with something.
*   **`required_tag="prey"`**: The collision trigger is activated by entities tagged as "prey".

### ExplosionComponent

Defines the explosion effect upon death.

*   **`trigger="ON_DEATH"`**: The explosion occurs when the entity dies.
*   **`explosion_radius="30"`**: The radius of the explosion.
*   **`explosion_sprite="data/particles/explosion_040_poof.xml"`**: The visual effect of the explosion.
*   **`damage="4"`**: The explosion deals 4 damage.
*   **`physics_explosion_power.min="2.3"`**, **`physics_explosion_power.max="3.6"`**: The force of the physics-based explosion.
*   **`audio_event_name="explosions/deer"`**: The sound effect played during the explosion.

### VariableStorageComponent

Stores custom variables.

*   **`name="projectile_file"`**, **`value_string="data/entities/projectiles/deck/exploding_deer.xml"`**: Identifies the entity's own file path.