---
title: ItemStashComponent Documentation for AI-Assisted Modding
source: https://noita.wiki.gg/wiki/Documentation:ItemStashComponent
category: modding-wiki
---

# ItemStashComponent Documentation for AI-Assisted Modding

This documentation covers the `ItemStashComponent` in Noita, a crucial component for defining how items are stored and retrieved within the game. Understanding this component is essential for modders looking to create custom item stashes, modify existing ones, or implement unique item management systems in their mods.

## Overview of ItemStashComponent

The `ItemStashComponent` is responsible for managing a collection of items that can be stored and later retrieved. This is commonly used for things like the player's inventory, chests, or other containers that hold items. Modders can leverage this component to customize the behavior of these storage mechanisms.

## Component Properties

The `ItemStashComponent` has several properties that can be configured to alter its functionality. These properties are typically defined within the entity's XML definition.

### `item_stash_component`

This is the main tag for the component.

| Property        | Type    | Description