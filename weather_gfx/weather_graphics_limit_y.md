---
title: Weather Graphics Limit Y
category: weather_gfx
---

# Weather Graphics Limit Y

This folder contains graphical assets for weather effects that are specifically designed to be clipped or limited by the vertical boundaries of the background image.

## Purpose

When the game generates background sprites, it checks this folder. If a weather graphic is positioned high enough to be clipped by `limit_background_image` and `background_image_height` (defined in `biome.xml`), the game will look for a file with the same name in this directory. If found, it will load and use that asset.

## Key Concepts

*   **Clipping:** Graphics are intentionally designed to be cut off at the top of the background.
*   **Vertical Limit:** The `limit_background_image` and `background_image_height` biome properties define the vertical boundary for these assets.
*   **Dynamic Loading:** Assets are loaded based on their position relative to the defined vertical limit.
*   **File Naming:** The game uses the same filename for the weather graphic and its corresponding clipped version in this folder.

## Usage

Modders can place custom weather graphics in this folder to create unique visual effects that interact with the game's background clipping mechanics. This allows for more dynamic and layered weather appearances.