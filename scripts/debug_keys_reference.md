---
title: Debug Keys Reference
category: scripts
---

# Debug Keys Reference

This document outlines the various debug keys available in Noita, primarily accessed through the `debug_keys.txt` file. These keys are invaluable for testing, debugging, and understanding game mechanics during development.

## General Debug Keybinds

These keys provide access to core debugging functionalities and information displays.

| Key Combination      | Action                                       | Description                                                                 |
| :------------------- | :------------------------------------------- | :-------------------------------------------------------------------------- |
| `F1`                 | Show / Hide Debug Key Map                    | Toggles the display of this debug key reference.                            |
| `F2`, `F3`, `F4`     | Screenshot / GIF Selection / GIF Recording   | Used for capturing images and creating animated GIFs of gameplay.           |
| `SHIFT + F4`         | Record Video (Fullscreen)                    | Starts recording the entire game screen as a video.                         |
| `CTRL + F4`          | Record Video (Selected Area)                 | Allows recording a specific portion of the screen as a video.               |
| `F5`                 | Toggle Debug Mode                            | Enables or disables the primary debug mode.                                 |
| `F5 + SHIFT`         | Open `debug_menu.lua`                        | Opens the main Lua script for custom debug menu functionalities.            |
| `F7 (+SHIFT/CTRL)`   | Open Various Debug Menus                     | Accesses a range of specialized debug menus depending on modifier keys.     |
| `F8`                 | Toggle Shaders On / Off                      | Enables or disables visual shaders for debugging purposes.                  |
| `F9`                 | Toggle Log Levels                            | Controls the verbosity of messages displayed in the debug log.              |
| `SHIFT + F9`         | Clear Debug Log                              | Empties the contents of the debug log window.                               |

## Debug Mode Specific Actions

Once debug mode is active (`F5`), a new set of keys becomes available for direct interaction with the game world.

### Player and Camera Control

| Key Combination        | Action                               | Description                                                                 |
| :--------------------- | :----------------------------------- | :-------------------------------------------------------------------------- |
| `RETURN`               | Spawn / Despawn Player               | Creates or removes the player character.                                    |
| `SHIFT + RETURN`       | Spawn New Player                     | Creates an additional player character.                                     |
| `ARROWS`               | Control Camera in Debug Mode         | Allows free movement of the camera within the game world.                   |
| `+CTRL+SHIFT+ALT`      | Adjust Camera Speed                  | Modifies how quickly the camera moves when using arrow keys.                |
| `CTRL + U`             | Pause / Unpause Simulation           | Stops or resumes the entire game simulation.                                |
| `CTRL+ALT+SPACE`       | Pause Some Simulation Elements       | Pauses specific aspects of the simulation, allowing for finer control.      |
| `CTRL + B`             | Pause Box2D Simulation               | Pauses only the physics simulation managed by the Box2D engine.             |

### Entity and Inspector Interaction

| Key Combination      | Action                               | Description                                                                 |
| :------------------- | :----------------------------------- | :-------------------------------------------------------------------------- |
| `I + Click`          | Open Hovered Entity in Inspector     | Opens a detailed inspector window for the entity currently under the mouse. |
| `BACKSPACE`          | Delete Selected Entity               | Removes the entity that is currently selected or hovered over.              |
| `CTRL + O`           | Load Entity (Open Inspector)         | Loads a specified entity and opens its inspector.                           |
| `CTRL+SHIFT+O`       | Load Previously Loaded Entity        | Reloads the entity that was last loaded via `CTRL + O`.                     |
| `CTRL + S`           | Save Inspected Entity                | Saves the currently inspected entity's data to a file.                      |
| `CTRL + I`           | Close Inspector                      | Closes the entity inspector window.                                         |
| `SHIFT + U`          | Save Selected Player Item Entity     | Saves the item currently held by the player to a file.                      |
| `ALT + SHIFT + U`    | Save Items as Separate XML Files     | Saves all items associated with the player as individual XML files.         |

### Material and Brush Tools

| Key Combination      | Action                               | Description                                                                 |
| :------------------- | :----------------------------------- | :-------------------------------------------------------------------------- |
| `CTRL+TAB`           | Toggle Material Menu                 | Opens or closes a menu for selecting and manipulating materials.            |
| `0-9 + SHIFT`        | Debug Brush Select                   | Selects a specific debug brush for material manipulation.                   |
| `CTRL+LMOUSE`        | Debug Draw Material                  | Paints the selected material onto the game world.                           |
| `CTRL+RMOUSE`        | Debug Destroy Material               | Removes material from the game world.                                       |
| `,`                  | Material Picker                      | Selects the material under the mouse cursor.                                |
| `SHIFT + ,`          | Blob Reaction                        | Triggers a specific material reaction (e.g., `rock_static` to `steam`).     |
| `CTRL + F`           | Load Image as Selected Material      | Uses an image file to define a new material for painting.                   |

### Spawning Entities and Objects

| Key Combination        | Action                               | Description                                                                 |
| :------------------- | :----------------------------------- | :-------------------------------------------------------------------------- |
| `H`                  | Huge Explosion                       | Creates a large explosion effect.                                           |
| `P`                  | Create Peasant                       | Spawns a basic "peasant" enemy.                                             |
| `SHIFT + P`          | Create Test Wand                     | Spawns a wand for testing purposes.                                         |
| `Y`                  | Create Barrel                        | Spawns a physics-enabled barrel.                                            |
| `M`                  | Create Vegetation Sprite             | Spawns a sprite representing vegetation.                                    |
| `R`                  | Load Ragdoll                         | Spawns a ragdoll entity (requires a `.txt` file).                           |
| `T`                  | Load Pixel Scene (Clears Rect)       | Loads a pixel scene and clears the current rectangular area.                |
| `SHIFT + T`          | Load Pixel Scene                     | Loads a pixel scene without clearing the current area.                      |
| `Z`                  | Load Zombie                          | Spawns a zombie enemy.                                                      |
| `SHIFT + Z`          | Load Shotgunner                      | Spawns a shotgunner enemy.                                                  |
| `SHIFT + ALT + Z`    | Load SMG Scavenger                   | Spawns an SMG scavenger enemy.                                              |
| `X`                  | Load Worm                            | Spawns a worm enemy.                                                        |
| `SHIFT + X`          | Load Big Worm                        | Spawns a larger variant of the worm enemy.                                  |
| `K`                  | Load Image as Pixel Sprite           | Loads an image and creates a pixel sprite from it.                          |
| `SHIFT + K`          | Use Image for "Loose a Chunk"        | Applies an image to create a "loose chunk" effect on terrain.               |
| `J`                  | Physics Joint                        | Creates a physics joint between two entities.                               |
| `J` (in debug mode)  | Create Particle Puff                 | Spawns a puff of particles.                                                 |
| `CTRL + Y`           | Load Foreground Sprite               | Loads a sprite intended for the foreground layer.                           |

## Debug Drawing and Visualizations

These keys toggle various visual overlays and debugging aids.

| Key Combination      | Action                               | Description                                                                 |
| :------------------- | :----------------------------------- | :-------------------------------------------------------------------------- |
| `B`                  | Toggle Debug Draw Box2D              | Shows or hides the debug visualizations for the Box2D physics engine.       |
| `SHIFT + B`          | Toggle Debug Draw Update Rects       | Displays or hides rectangles indicating areas being updated.                |
| `V`                  | Toggle Smooth Rendering              | Enables or disables smooth rendering effects.                               |
| `N`                  | Toggle CollisionChecker Debug Drawings | Shows or hides debug drawings related to the collision detection system.    |
| `SHIFT + O`          | Toggle Path Finding Grid Display     | Shows or hides the pathfinding grid used by AI.                             |

## World and Configuration Debugging

| Key Combination      | Action                               | Description                                                                 |
| :------------------- | :----------------------------------- | :-------------------------------------------------------------------------- |
| `L`                  | Open World State Entity              | Opens a debug view of the current world state.                              |
| `CTRL + L`           | Open Weather / Parallax Config       | Accesses configuration settings for weather effects and parallax backgrounds. |
| `CTRL + R`           | Reload Pixel Scenes                  | Reloads all pixel scene data.                                               |
| `ALT + R`            | Convert Ground into TNT              | Transforms the ground material into TNT.                                    |

## Profiler Tools

These keys provide access to performance analysis tools.

| Key Combination        | Action                               | Description                                                                 |
| :------------------- | :----------------------------------- | :-------------------------------------------------------------------------- |
| `CTRL + P`           | Open Profiler Window                 | Opens the main profiler window, listing all profiled components.            |
| `CTRL + SHIFT + P`   | Open Profiler Bars                   | Displays profiler data in a bar graph format.                               |
| `CTRL + ALT + P`     | Open Frame Viewer                    | Opens a tool for analyzing individual game frames.                          |

## Miscellaneous Debugging and Testing Keys

| Key Combination      | Action                               | Description                                                                 |
| :------------------- | :----------------------------------- | :-------------------------------------------------------------------------- |
| `F10`                | Load Image, Create Physics Body      | Loads an image and creates a physics body with a random material.           |
| `F12`                | Trailer Recording Mode               | Activates a mode optimized for recording trailers.                          |
| `ALT + T`            | Test Randomness of Items             | Triggers a test of the item generation randomness.                          |
| `CTRL + C`           | Take Control of Selected Entity      | Allows direct control of the currently selected entity.                     |
| `ALT + C`            | Restart Game                         | Resets the game to its initial state.                                       |
| `ALT + 0-9`          | Change Language                      | Switches the game's language to various different options.                  |