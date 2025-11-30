---
title: Player Entity - Debug Configuration
category: entities
---

# Player Entity - Debug Configuration

This document details the configuration for the player entity, specifically within a debug context. It outlines key components and attributes that define player behavior, physics, and visual representation.

## Core Entity Attributes

*   **name**: `DEBUG_NAME:player` - Identifies this entity as a debug version of the player.
*   **tags**: `mortal,human,hittable,prey,player_unit` - Defines the player's fundamental characteristics and interactions.

## Key Components

### Transform Component

*   **rotation**: `0` - Initial rotation of the player entity.
*   **scale.x**: `1` - Initial scale along the X-axis.
*   **scale.y**: `1` - Initial scale along the Y-axis.

### Hotspot Components

These define specific points on the player entity for various interactions.

*   **hand**: `sprite_hotspot_name="hand"` - Location for hand-related actions.
*   **shoot\_pos**: `offset.x="0", offset.y="-2"` - Position from which projectiles are fired.
*   **kick\_pos**: `offset.x="0", offset.y="2"` - Position for kicking actions.
*   **crouch\_sensor**: `offset.x="0", offset.y="-14"` - Sensor for detecting crouched state.

### PlatformShooterPlayerComponent

Manages player movement and camera behavior in a platforming context.

*   **center\_camera\_on\_this\_entity**: `1` - Camera will follow the player.
*   **aiming\_reticle\_distance\_from\_character**: `60` - Distance of the aiming reticle from the player.
*   **camera\_max\_distance\_from\_character**: `50` - Maximum camera distance.
*   **move\_camera\_with\_aim**: `1` - Camera movement is tied to aiming.
*   **eating\_area\_min/max**: Defines the area for eating mechanics.

### PathFindingGridMarkerComponent

Used for pathfinding calculations.

*   **player\_marker\_radius**: `100.0` - Radius for pathfinding markers.
*   **marker\_offset\_y**: `-3` - Vertical offset for the marker.

### CharacterCollisionComponent

Handles collision detection and crushing mechanics.

*   **getting\_crushed\_threshold**: `6` - Threshold for being crushed.
*   **moving\_up\_before\_getting\_crushed\_threshold**: `6` - Threshold for moving up before crushing.

### CharacterDataComponent

Core data for character physics and behavior.

*   **platforming\_type**: `2` - Type of platforming behavior.
*   **check\_collision\_max\_size\_x/y**: `4` - Maximum collision box size.
*   **climb\_over\_y**: `4` - Height the character can climb over.
*   **collision\_aabb\_min/max\_x/y**: Defines the character's Axis-Aligned Bounding Box.
*   **eff\_hg\_...**: Various parameters related to a "hit ground" effect, including position, size, velocity, and damage.
*   **effect\_hit\_ground**: `1` - Enables the hit ground effect.
*   **fly\_time\_max**: `3.0` - Maximum duration of flight.
*   **fly\_recharge\_spd**: `0.4` - Recharge speed for flight.
*   **gravity**: `0` - Disables gravity for this debug player.
*   **buoyancy\_check\_offset\_y**: `-7` - Offset for buoyancy checks.

### GenomeDataComponent

Defines the player's place in the game's ecosystem.

*   **herd\_id**: `player` - Identifier for the player's herd.
*   **food\_chain\_rank**: `20` - Rank in the food chain.
*   **is\_predator**: `1` - Indicates the player is a predator.

### CharacterPlatformingComponent

Fine-tunes platforming movement and abilities.

*   **jump\_velocity\_y**: `-165` - Vertical jump force.
*   **jump\_velocity\_x**: `65` - Horizontal jump force.
*   **fly\_speed\_max\_up/down**: Maximum vertical flight speeds.
*   **fly\_speed\_mult**: Multiplier for flight speed.
*   **mouse\_look**: `1` - Enables mouse look.
*   **pixel\_gravity**: `600` - Gravity applied per pixel.
*   **run\_velocity**: `154` - Running speed.
*   **accel\_x**: `0.15` - Horizontal acceleration.
*   **velocity\_min/max\_x/y**: Limits for velocity.

### ControlsComponent

Configures player input handling.

*   **gamepad\_fire\_on\_thumbstick\_extend**: `0` - Disables firing on thumbstick extend.
*   **gamepad\_indirect\_aiming\_enabled**: `0` - Disables indirect gamepad aiming.
*   **id\_button\_...**: Mappings for various controller buttons (set to `0` for debug).

### DamageModelComponent

Manages player health and damage interactions.

*   **hp**: `3` - Starting health points.
*   **invincibility\_frames**: `60` - Frames of invincibility after taking damage.
*   **materials\_that\_damage**: Lists materials that inflict damage (e.g., `acid,lava`).
*   **materials\_how\_much\_damage**: Corresponding damage values for each material.
*   **damage\_multipliers**: Modifiers for specific damage types (e.g., `explosion="0.35"`).

### HitboxComponent

Defines the player's collision areas.

*   **aabb\_max/min\_x/y**: Defines the bounding box for the standard hitbox.
*   **is\_player**: `1` - Marks this hitbox as belonging to the player.
*   A second `HitboxComponent` with `_tags="crouched"` and `_enabled="0"` defines a smaller hitbox for the crouched state.

### SpriteComponent

Handles visual rendering of the player.

*   **image\_file**: `data/enemies_gfx/player.xml` - Path to the player's sprite sheet.
*   **rect\_animation**: `walk` - Default animation.
*   **z\_index**: `0.6` - Rendering layer.
*   A second `SpriteComponent` with `_tags="aiming_reticle"` renders the aiming cursor.

### SpriteParticleEmitterComponent

*   **_tags**: `jetpack` - Associated with the jetpack effect.
*   **sprite\_file**: `data/particles/jetpack_smoke.xml` - Particle effect for jetpack smoke.
*   **is\_emitting**: `1` - The particle emitter is active.

### LightComponent

Defines a light source originating from the player.

*   **r, g, b**: `255, 220, 190` - Light color.
*   **radius**: `750` - Light radius.

### Entity: cape

Includes a nested entity for the player's cape, inheriting transform properties.

### MaterialInventoryComponent & IngestionComponent

These components handle the player's ability to interact with and ingest materials.

### LuaComponent

*   **script\_inhaled\_material**: `data/scripts/magic/alchemy.lua` - Script for inhaled materials.
*   **script\_ingested\_material**: `data/scripts/magic/alchemy.lua` - Script for ingested materials.
*   A second `LuaComponent` with `script_source_file="data/scripts/magic/alchemy_init.lua"` executes initialization scripts.