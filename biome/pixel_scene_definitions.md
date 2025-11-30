---
title: Pixel Scene Definitions
category: biome
---

# Pixel Scene Definitions

This document outlines the structure and key elements for defining `PixelScene` elements within Noita's data files. Pixel scenes are used to define pre-fabricated chunks of terrain, background elements, and entities that can be placed within biomes.

## Core Concepts

`PixelScenes` are the top-level container for defining these scene elements. They are typically found in `data/biome/` and reference other data files for their visual and physical properties.

There are two primary ways to define pixel scenes:

1.  **Referencing external `.xml` files:** Using `<File>` tags within `<PixelSceneFiles>` to include pre-defined scene layouts.
2.  **Directly embedding scene definitions:** Using `<PixelScene>` tags within `<mBufferedPixelScenes>` to define scenes inline.

## Key Elements and Attributes

### `<PixelSceneFiles>`

This section lists external `.xml` files that contain definitions for spliced pixel scenes. These are essentially reusable biome chunks.

*   **`<File>`**: Specifies the path to an external `.xml` file that defines a pixel scene.

    *   **Example:**
        ```xml
        <File>data/biome_impl/spliced/lavalake2.xml</File>
        ```

### `<BackgroundImages>`

This section defines static background images that can be placed within the game world. These are purely visual and do not affect gameplay mechanics.

*   **`<Image>`**: Defines a background image.
    *   **`filename`**: The path to the image file (e.g., `.png`).
    *   **`x`**: The horizontal position of the image.
    *   **`y`**: The vertical position of the image.

    *   **Example:**
        ```xml
        <Image filename="data/biome_impl/hidden/boss_arena.png" x="3425" y="12650" ></Image>
        ```

### `<mBufferedPixelScenes>`

This section allows for the direct definition of pixel scenes, including their visual components, material properties, and placement.

*   **`<PixelScene>`**: Defines an embedded pixel scene.
    *   **`material_filename`**: (Required) The path to the `.png` file defining the materials (terrain) of the scene. This file uses color mapping to determine material types.
    *   **`colors_filename`**: (Optional) The path to a `.png` file defining the visual colors of the scene. If not provided, the `material_filename` might also be used for visual representation.
    *   **`background_filename`**: (Optional) The path to a background image for this specific scene.
    *   **`pos_x`**: The horizontal position where the scene will be placed.
    *   **`pos_y`**: The vertical position where the scene will be placed.
    *   **`clean_area_before`**: (Boolean, 0 or 1) If set to 1, the area where the scene is placed will be cleared of existing entities before placement.
    *   **`skip_biome_checks`**: (Boolean, 0 or 1) If set to 1, biome restrictions for placing this scene are ignored.
    *   **`skip_edge_textures`**: (Boolean, 0 or 1) If set to 1, edge textures for this scene might be skipped.
    *   **`just_load_an_entity`**: (Optional) If this attribute is present, the `PixelScene` will instead load and place the specified entity at the given `pos_x` and `pos_y`. This is useful for placing individual entities as part of a scene.

    *   **Example (Material and Color based scene):**
        ```xml
        <PixelScene DEBUG_RELOAD_ME="0" background_filename="data/biome_impl/snowcastle/forge_background.png" clean_area_before="0" colors_filename="data/biome_impl/snowcastle/forge_visual.png" material_filename="data/biome_impl/snowcastle/forge.png" pos_x="1464" pos_y="5976" skip_biome_checks="1" skip_edge_textures="0" >
        </PixelScene>
        ```
    *   **Example (Entity loading):**
        ```xml
        <PixelScene pos_x="-1824" pos_y="-1270" just_load_an_entity="data/entities/props/physics_fungus.xml" />
        ```

## Summary of Key Attributes for `<PixelScene>`

| Attribute              | Description                                                                                             | Type    | Required | Notes