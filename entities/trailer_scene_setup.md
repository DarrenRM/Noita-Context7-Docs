---
title: Trailer Scene Setup
category: entities
---

# Trailer Scene Setup

This script defines the setup for a trailer scene in Noita, focusing on camera movement, loading specific pixel scenes, and potentially spawning entities. It's designed to be run asynchronously and utilizes utility functions for camera control and scene loading.

## Key Functions and Attributes

### `async(function() ... end)`
This wraps the entire trailer setup logic, allowing it to run asynchronously without blocking the main game thread.

### Camera Control
The script manipulates the game camera to control the view during the trailer.

*   **`GameSetCameraFree( true )`**: Enables free camera movement, disabling its usual tracking of the player.
*   **`GameSetCameraPos( x, y )`**: Sets the camera's position to the specified `x` and `y` coordinates. This is used to move the camera to different points to load specific scene elements and create visual transitions.
*   **`wait(frames)`**: Pauses the execution for a specified number of frames, creating delays between camera movements or scene loading events.

### Scene Loading
The `LoadPixelScene` function is crucial for populating the trailer environment with visual elements.

*   **`LoadPixelScene( image_path, visual_image_path, x, y, material_name, is_static )`**:
    *   `image_path`: Path to the image file defining the scene's geometry.
    *   `visual_image_path`: Path to the image file defining the scene's visual appearance.
    *   `x`, `y`: Coordinates where the scene will be loaded.
    *   `material_name`: (Optional) Specifies a material to apply to the scene.
    *   `is_static`: (Optional) Determines if the scene is static.

The script loads several pixel scenes related to "nolla_games":

*   `data/biome_impl/nolla_games.png`
*   `data/biome_impl/nolla_games_visual.png`
*   `data/biome_impl/nolla_games_bottom.png`
*   `data/biome_impl/nolla_games_bottom_visual.png`
*   `data/biome_impl/nolla_games_left.png`
*   `data/biome_impl/nolla_games_left_visual.png`
*   `data/biome_impl/nolla_games_right.png`
*   `data/biome_impl/nolla_games_right_visual.png`

These are positioned relative to a base `px` and `py` coordinate.

### Debugging and Entity Loading
*   **`DebugEnableTrailerMode()`**: Activates a special trailer mode, likely for disabling certain game elements or enabling specific debugging features relevant to trailers.
*   **`EntityLoad( entity_xml_path, x, y )`**: (Commented out) This function would be used to load specific entities (like props or animals) into the scene at given coordinates. The commented lines suggest potential entities like `physics_logo.xml` and `crawler.xml` were considered.

### Projectile Spawning
*   **`shoot_projectile( entity_id, projectile_xml_path, x, y, angle, speed )`**: (Commented out) This function is intended to spawn a projectile from a specified entity. The commented line shows an example of spawning a "meteor" projectile.

## Summary

This script is a foundational piece for creating cinematic sequences or trailers within Noita. It demonstrates how to control the camera, load custom visual environments using pixel scenes, and prepare the game state for a trailer presentation. The commented-out sections provide hints about further potential functionalities like entity spawning and projectile effects.