---
title: Decoy Entity
category: entities
---

# Decoy Entity

This document describes the `decoy.xml` entity, which functions as a player decoy in Noita. It's designed to mimic player behavior and appearance for a limited time.

## Key Components and Attributes

### Entity Tags
The entity is tagged with `prey`, `mortal`, and `teleportable_NOT`. This indicates it can be preyed upon, is mortal, and cannot be teleported.

### VelocityComponent
Controls the entity's movement physics.
- `gravity_y`: "400" - Standard gravity effect.
- `air_friction`: "0.55" - Moderate air resistance.
- `terminal_velocity`: "1000" - Maximum falling speed.

### SimplePhysicsComponent
Enables basic physics interactions for the entity.

### LifetimeComponent
Determines how long the decoy exists.
- `lifetime`: "600" - The decoy will exist for 600 game frames (approximately 10 seconds).

### GenomeDataComponent
Provides biological data, influencing AI and interactions.
- `herd_id`: "player" - Identifies the decoy as belonging to the player's "herd" for AI purposes.
- `food_chain_rank`: "20" - A rank indicating its position in the food chain.
- `is_predator`: "1" - Marks the decoy as a predator.

### HitboxComponent
Defines the entity's collision boundaries.
- `aabb_max_x`: "3"
- `aabb_max_y`: "0"
- `aabb_min_x`: "-3"
- `aabb_min_y`: "-16"
- `is_enemy`: "0" - Not an enemy.
- `is_item`: "0" - Not an item.
- `is_player`: "1" - Crucially, it's identified as the player for certain game mechanics.

### PathFindingGridMarkerComponent
Helps the AI navigate around the entity.
- `marker_offset_y`: "-3"
- `marker_work_flag`: "8"

### LightComponent
Gives the decoy a visual light source.
- `r`, `g`, `b`: "50", "100", "255" - A blueish light.
- `radius`: "64" - The range of the light.
- `fade_out_time`: "0.75" - How long the light takes to fade.

### SpriteComponent
Defines the visual appearance of the decoy.
- `alpha`: "0.5" - The decoy is semi-transparent.
- `image_file`: "data/enemies_gfx/player.xml" - Uses the player's graphics.
- `next_rect_animation`, `rect_animation`: "stand" - Uses the player's standing animation.
- `offset_x`, `offset_y`: "6", "18" - Adjusts the sprite's position.

### SpriteAnimatorComponent
Handles sprite animations.

### HotspotComponent
Defines specific points on the sprite for other components to attach to.
- `sprite_hotspot_name`: "cape" - Likely used for attaching visual elements like capes.