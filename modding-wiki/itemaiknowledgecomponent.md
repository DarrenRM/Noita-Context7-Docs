---
title: ItemAIKnowledgeComponent
source: https://noita.wiki.gg/wiki/Documentation:ItemAIKnowledgeComponent
category: modding-wiki
---

# ItemAIKnowledgeComponent

This documentation page explains the `ItemAIKnowledgeComponent` in Noita, a crucial component for defining how items interact with and are perceived by enemy AI. Understanding this component is essential for modders looking to create custom items that behave realistically or in novel ways within the game's AI systems.

## Overview

The `ItemAIKnowledgeComponent` dictates what information an AI entity has about a specific item. This includes whether the AI knows the item exists, its type, and potentially its properties or effects. This knowledge influences the AI's decision-making process, such as whether to pick up an item, avoid it, or react to its presence.

## Component Properties

The `ItemAIKnowledgeComponent` is defined within an item's XML file and contains several properties that control the AI's perception.

### `item_knowledge_type`

This property defines the general category of knowledge the AI has about the item.

| Value             | Description