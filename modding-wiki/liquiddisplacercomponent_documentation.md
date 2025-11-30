---
title: LiquidDisplacerComponent Documentation
source: https://noita.wiki.gg/wiki/Documentation:LiquidDisplacerComponent
category: modding-wiki
---

# LiquidDisplacerComponent Documentation

This documentation covers the `LiquidDisplacerComponent` in Noita, a crucial component for creating entities that interact with and displace liquids. Understanding this component is essential for modders who wish to implement custom liquids, environmental effects, or entities that behave realistically within the game's fluid dynamics.

## Overview

The `LiquidDisplacerComponent` is used to define how an entity interacts with liquids in Noita. It allows entities to displace liquids, effectively pushing them out of the way as the entity moves or exists. This is fundamental for creating effects like water currents caused by movement, or objects that float or sink based on their interaction with different liquid types.

## Component Properties

The `LiquidDisplacerComponent` has several properties that can be configured in an entity's XML definition to control its liquid displacement behavior.

### `liquid_material`

This property specifies the type of liquid that the component will interact with. If not specified, it will interact with all liquids.

| Property        | Type   | Description