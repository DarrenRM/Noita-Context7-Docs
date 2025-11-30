---
title: Eyespot Check Script
category: scripts
---

# Eyespot Check Script

This script is designed to be attached to an entity that acts as an "eyespot." When a player unit and an entity with the "tripping_extreme" tag are detected within a certain radius, it triggers a music event, loads a specific item (likely a book), and then destroys the eyespot entity.

## Key Functionality

*   **Proximity Detection:** Checks for the presence of a player unit and an entity tagged "tripping_extreme" within a 64-unit radius.
*   **Conditional Trigger:** The core logic only executes if *both* a player and a "tripping\_extreme" entity are found.
*   **Item Loading:** Loads an entity from an XML file. The specific file is determined by a `value_string` stored in a `VariableStorageComponent` named "eyespot\_object" on the eyespot entity itself. The base path for these items is `data/entities/items/books/`.
*   **Music Event:** Triggers a specific music event (`music/oneshot/tripping_balls_02`) when the conditions are met.
*   **Self-Destruction:** The eyespot entity is destroyed after successfully loading the item and triggering the music.

## Key Attributes/Elements

| Attribute/Element        | Description