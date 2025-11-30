---
title: Trailer Scene Setup - Demonic Altar
category: entities
---

# Trailer Scene Setup - Demonic Altar

This script defines the setup for a specific trailer scene, focusing on the "Demonic Altar" biome. It loads the biome, places a trailer wand, and then strategically loads various "altar torch" entities and other visual elements to create a dramatic effect. The script also includes timed loading of "midas" and "gold effect" entities, followed by the destruction of the altar with loose chunks and specific entity loads to simulate a collapse.

## Key Functions and Logic

The script utilizes asynchronous loading and camera manipulation to control the pacing and visual presentation of the trailer scene.

### Core Logic

*   **`async(function() ... end)`**: Encapsulates the trailer sequence, allowing for timed events and waits.
*   **`GameSetCameraFree( true )`**: Enables free camera movement for cinematic control.
*   **`GameSetCameraPos( x, y )`**: Sets the camera's position in the game world.
*   **`wait(seconds)`**: Pauses the script execution for a specified duration.
*   **`DebugEnableTrailerMode()`**: Activates trailer-specific debug features.
*   **`LoadPixelScene( biome_png, visual_png, x, y, background_png, is_background_layer )`**: Loads a pixel-based biome scene.
*   **`EntityLoad( xml_path, x, y )`**: Loads an entity from its XML definition at a given position.
*   **`LooseChunk( x, y, png_path )`**: Creates a destructible chunk of terrain at a specified location.

### Scene Setup and Progression

1.  **Initial Camera Movement**: The camera is moved to force the loading of pixel scene data.
2.  **Demonic Altar Biome Loading**: The `demonic_altar` biome is loaded at a specific world coordinate (`px`, `py`).
3.  **Trailer Wand Placement**: A `trailer_wand.xml` entity is placed near the center of the scene.
4.  **Altar Torch Placement**: Multiple instances of `altar_torch_midas.xml` are strategically positioned around the altar.
5.  **Timed Midas and Gold Effect**: After a significant delay, `midas.xml` and `gold_effect.xml` are loaded, suggesting a transformation or event.
6.  **Altar Destruction Sequence**: A series of `LooseChunk` calls with different `altar_chunk` PNGs simulate the altar breaking apart.
7.  **Final Entity Loads**: `midas_chunks.xml` and `midas_sand.xml` are loaded to complete the visual effect of the altar's destruction.

## Key Entities Loaded

The script focuses on loading specific entities to build the trailer scene.

| Entity Path                               | Description                                     |
| :---------------------------------------- | :---------------------------------------------- |
| `data/entities/items/trailer_wand.xml`    | A wand specifically for trailer purposes.       |
| `data/entities/trailer/altar_torch_midas.xml` | Torches associated with the demonic altar.      |
| `data/entities/trailer/midas.xml`         | Likely an entity related to a "Midas" effect.   |
| `data/entities/trailer/gold_effect.xml`   | Visual effect representing gold.                |
| `data/entities/trailer/midas_chunks.xml`  | Chunks of debris related to the Midas effect.   |
| `data/entities/trailer/midas_sand.xml`    | Sand or particulate effect related to Midas.    |

## Key Biome/Scene Elements

| Element                                     | Description                                                              |
| :------------------------------------------ | :----------------------------------------------------------------------- |
| `data/biome_impl/demonic_altar.png`         | The primary pixel data for the demonic altar biome.                      |
| `data/biome_impl/demonic_altar_visual.png`  | Visual layer for the demonic altar biome.                                |
| `data/biome_impl/demonic_altar_background.png` | Background layer for the demonic altar biome.                            |
| `data/entities/trailer/altar_chunk_XX.png`  | PNG images used to define the shape of destructible altar chunks.        |

## Modding Considerations

*   **Timing**: The `wait()` calls are crucial for the trailer's pacing. Adjusting these will alter the sequence of events.
*   **Entity Placement**: The `px` and `py` variables, along with the offsets in `EntityLoad` and `LoadPixelScene`, define the scene's location and layout.
*   **Visual Assets**: The PNG files for biome data and loose chunks are essential for the visual appearance of the scene.
*   **Trailer Mode**: `DebugEnableTrailerMode()` might disable certain game mechanics or enable specific debug visuals relevant to trailers.