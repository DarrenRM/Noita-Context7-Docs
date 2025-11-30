---
title: AttachToEntityComponent
source: https://noita.wiki.gg/wiki/Documentation:AttachToEntityComponent
category: modding-wiki
---

# AttachToEntityComponent

This documentation page explains the `AttachToEntityComponent` in Noita, a crucial component for creating entities that dynamically attach to other entities. Understanding this component is vital for modders who wish to implement complex behaviors like projectiles that follow a target, effects that stick to characters, or any entity that needs to maintain a relative position to another.

## Overview

The `AttachToEntityComponent` allows an entity to attach itself to another entity. This attachment can be configured to maintain a specific offset and rotation relative to the parent entity. It's a powerful tool for creating dynamic and interactive elements within the game world.

## Component Properties

The `AttachToEntityComponent` has the following properties that can be configured in your entity's XML definition:

| Property Name | Type    | Description