---
title: StreamingKeepAliveComponent
source: https://noita.wiki.gg/wiki/Documentation:StreamingKeepAliveComponent
category: modding-wiki
---

# StreamingKeepAliveComponent

This documentation page explains the `StreamingKeepAliveComponent` in Noita, a crucial component for managing the lifecycle of entities within the game's streaming world. Understanding this component is vital for modders who wish to create persistent or dynamically managed entities that interact correctly with Noita's world streaming system.

## Overview

The `StreamingKeepAliveComponent` is designed to ensure that specific entities remain loaded and active even when they are outside the player's immediate vicinity or when the game's world streaming system would normally unload them. This is particularly useful for entities that need to perform ongoing actions, maintain state, or be available for interaction at any time, regardless of player proximity.

## Component Properties

The `StreamingKeepAliveComponent` has the following properties that can be configured in an entity's XML definition:

| Property Name | Type    | Description