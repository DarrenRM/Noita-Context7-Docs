---
title: PathFindingGridMarkerComponent
source: https://noita.wiki.gg/wiki/Documentation:PathFindingGridMarkerComponent
category: modding-wiki
---

# PathFindingGridMarkerComponent

This documentation page details the `PathFindingGridMarkerComponent` in Noita, a crucial component for defining how entities interact with the game's pathfinding system. Understanding this component is essential for modders who wish to create custom entities with specific movement behaviors or influence how existing entities navigate the game world.

## Overview

The `PathFindingGridMarkerComponent` is used to mark specific grid cells as traversable or non-traversable for pathfinding entities. This allows for fine-grained control over where AI agents can and cannot go, enabling the creation of custom environments, obstacles, and movement restrictions.

## Component Properties

The `PathFindingGridMarkerComponent` has the following properties that can be configured in an entity's XML definition:

| Property Name | Type    | Description