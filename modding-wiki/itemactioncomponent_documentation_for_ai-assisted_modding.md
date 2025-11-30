---
title: ItemActionComponent Documentation for AI-Assisted Modding
source: https://noita.wiki.gg/wiki/Documentation:ItemActionComponent
category: modding-wiki
---

# ItemActionComponent Documentation

This documentation details the `ItemActionComponent` in Noita, a crucial component for defining how items behave when used. Understanding and modifying this component is essential for creating custom items with unique effects, from simple projectile firing to complex spell interactions. This guide provides the necessary information, including component properties, data structures, and examples, to effectively leverage `ItemActionComponent` in your Noita mods.

## Understanding ItemActionComponent

The `ItemActionComponent` is attached to entities that represent usable items in Noita. It dictates the primary action an item performs when the player "uses" it (typically by pressing the action button). This component is fundamental for creating custom weapons, tools, and consumables with distinct functionalities.

### Core Functionality

The `ItemActionComponent` defines the following key aspects of an item's action:

*   **Action Type:** What kind of action the item performs (e.g., firing a projectile, casting a spell, applying an effect).
*   **Targeting:** How the action targets its effect (e.g., aiming, self-application, area of effect).
*   **Execution Logic:** The specific parameters and conditions that govern the action's execution.

### Component Properties

The `ItemActionComponent` has several properties that can be configured within the item's XML definition. These properties control various aspects of the item's action.

| Property Name        | Type    | Description