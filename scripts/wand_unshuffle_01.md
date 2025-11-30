---
title: Wand Unshuffle 01
category: scripts
---

# Wand Unshuffle 01

This script defines a procedural wand generation configuration. It utilizes the `generate_gun` function from `gun_procedural.lua` to create a wand with specific characteristics.

## Key Attributes

*   **`generate_gun( 25, 1, true )`**: This is the core function call that defines the wand's properties.
    *   **`25`**: Likely represents the base spell count or a similar magnitude for the wand.
    *   **`1`**: Could indicate a specific wand type or a modifier value.
    *   **`true`**: This boolean likely enables or disables a particular feature, such as shuffling of spells or a specific generation algorithm.

## Purpose

This script is intended to be used within Noita's modding framework to procedurally generate a wand. The specific values passed to `generate_gun` suggest a wand with a moderate number of spells and a particular generation behavior enabled.

## Usage

To use this script, it should be placed within the `data/scripts/gun/procedural/` directory of a Noita mod. The game will then load and execute this script during its initialization or when a wand of this type is intended to be generated.