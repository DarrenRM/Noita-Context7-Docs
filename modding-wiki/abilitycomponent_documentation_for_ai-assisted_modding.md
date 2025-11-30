---
title: AbilityComponent Documentation for AI-Assisted Modding
source: https://noita.wiki.gg/wiki/Documentation:AbilityComponent
category: modding-wiki
---

# AbilityComponent Documentation for AI-Assisted Modding

This documentation explains the `AbilityComponent` in Noita, a crucial component for defining character abilities and actions. Understanding `AbilityComponent` is essential for modders looking to create new spells, modify existing ones, or implement custom character behaviors.

## Understanding AbilityComponent

The `AbilityComponent` is a fundamental entity component in Noita that governs how entities can perform actions or "abilities." It's primarily used for defining spells and the mechanics behind their casting and execution.

### Core Functionality

The `AbilityComponent` dictates:

*   **What ability can be cast:** This is often linked to a specific spell entity.
*   **How the ability is triggered:** This can be through player input, AI, or other game events.
*   **The effects of the ability:** This includes visual effects, damage, status effects, and more, often defined by other components or scripts.

### Key Properties and Their Modding Implications

The `AbilityComponent` has several properties that modders can manipulate to alter ability behavior.

#### `ability_type`

This property defines the fundamental type of ability being used. It's crucial for distinguishing between different kinds of actions.

| Value             | Description