---
title: Freeze Field Perk
category: data/entities
---

# Freeze Field Perk

This entity defines the "Freeze Field" perk in Noita. It functions by inheriting from a base material conversion entity and applying specific freezing effects.

## Core Functionality

The Freeze Field perk utilizes the `MagicConvertMaterialComponent` to transform various liquids and materials into their frozen counterparts within a specified radius.

### Key Components

*   **`InheritTransformComponent`**: Standard component for inheriting transform properties.
*   **`Base file="data/entities/misc/material_converter_freeze.xml"`**: This indicates that the Freeze Field perk is built upon a pre-existing entity responsible for material conversion, specifically for freezing effects. This promotes code reuse and modularity.

### `MagicConvertMaterialComponent` Attributes

The primary mechanism for the freezing effect is the `MagicConvertMaterialComponent`. While the provided XML shows an inherited configuration, the commented-out sections reveal the specific conversions and parameters that would typically be applied.

Here are the key attributes observed and implied:

| Attribute           | Description