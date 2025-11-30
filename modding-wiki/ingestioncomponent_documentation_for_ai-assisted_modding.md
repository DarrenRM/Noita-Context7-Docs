---
title: IngestionComponent Documentation for AI-Assisted Modding
source: https://noita.wiki.gg/wiki/Documentation:IngestionComponent
category: modding-wiki
---

# IngestionComponent Documentation for AI-Assisted Modding

This documentation explains the `IngestionComponent` in Noita, a crucial component for defining how entities interact with and consume other entities. Understanding this component is vital for modders who wish to create custom interactions, modify existing consumption mechanics, or introduce new behaviors related to entity absorption.

## Understanding the IngestionComponent

The `IngestionComponent` dictates the rules and effects associated with an entity "ingesting" or consuming another entity. This is fundamental for mechanics like enemies eating projectiles, players consuming potions, or even environmental hazards absorbing entities.

### Component XML Structure

The `IngestionComponent` is defined within an entity's XML file. Here's a basic structure:

```xml
<ingestion
    ...
/>
```

### Key Attributes

The `IngestionComponent` has several attributes that control its behavior.

| Attribute Name        | Type    | Description