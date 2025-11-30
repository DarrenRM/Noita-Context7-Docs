---
title: Item Alchemy Component
source: https://noita.wiki.gg/wiki/Documentation:ItemAlchemyComponent
category: modding-wiki
---

# Item Alchemy Component

This documentation explains the `ItemAlchemyComponent` in Noita, a crucial component for defining how items interact with the alchemy system. Understanding this component is essential for modders who wish to create custom alchemy recipes, modify existing ones, or implement new item behaviors related to alchemy.

## Overview

The `ItemAlchemyComponent` is attached to items and defines their role in the alchemy system. It dictates what an item can be transformed into and what ingredients it requires for transformation. This component is fundamental for any mod that alters or expands Noita's alchemy mechanics.

## Component Structure

The `ItemAlchemyComponent` is defined within an item's XML file. It contains a list of `alchemy_item` entries, each representing a potential alchemy transformation.

### `alchemy_item` Entry

Each `alchemy_item` entry defines a single alchemy recipe.

| Attribute      | Type    | Description