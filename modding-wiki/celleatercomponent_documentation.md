---
title: CellEaterComponent Documentation
source: https://noita.wiki.gg/wiki/Documentation:CellEaterComponent
category: modding-wiki
---

# CellEaterComponent Documentation

This documentation page details the `CellEaterComponent` in Noita, a crucial component for entities that consume or interact with "cells" within the game's mechanics. Understanding this component is vital for modders looking to create custom enemies, environmental hazards, or unique gameplay interactions that involve cell consumption.

## Overview

The `CellEaterComponent` dictates how an entity behaves when it encounters and consumes cells. This includes defining the types of cells it can consume, the effects of consumption, and any associated visual or auditory feedback. Modding this component allows for the creation of entities with unique feeding behaviors and impacts on the game's cell-based systems.

## Component Properties

The `CellEaterComponent` has several properties that can be configured within an entity's XML definition. These properties control the core functionality of the cell-eating behavior.

### `eat_cell_type`

This property specifies the type of cell the entity is designed to eat.

| Value       | Description