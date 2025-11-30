---
title: Homunculus Initialization Script
category: scripts
---

# Homunculus Initialization Script

This script initializes a Homunculus entity in Noita, defining its behavior, appearance, and stats based on a specified or randomly chosen "type".

## Core Functionality

The script dynamically configures a Homunculus entity upon its creation. It reads a `homunculus_type` variable from the entity's `VariableStorageComponent` to determine its specific variant. If no type is specified, it randomly selects one. It then applies the relevant components and values to the entity.

## Homunculus Types

The script defines several distinct types of Homunculi, each with unique attack patterns and visual appearances.

### Type Definitions

| Name     | Description