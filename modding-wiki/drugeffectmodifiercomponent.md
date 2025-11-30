---
title: DrugEffectModifierComponent
source: https://noita.wiki.gg/wiki/Documentation:DrugEffectModifierComponent
category: modding-wiki
---

# DrugEffectModifierComponent

This documentation page explains the `DrugEffectModifierComponent` in Noita, a crucial component for modders looking to alter or create new drug effects. Understanding this component allows for fine-grained control over how drugs impact the player, opening up possibilities for unique gameplay mechanics and challenges.

## Overview

The `DrugEffectModifierComponent` is used to define and apply modifiers to various aspects of the player's state when a drug effect is active. These modifiers can affect attributes like movement speed, damage, mana, and more, providing a powerful tool for custom drug effects in your mods.

## Component Structure

The `DrugEffectModifierComponent` is an XML component that can be added to entities. Its primary function is to define a list of modifiers that are applied when the associated drug effect is active.

### Attributes

The `DrugEffectModifierComponent` itself does not have direct attributes that you modify in the XML. Instead, it contains a list of `Modifier` elements, each defining a specific modification.

### Modifier Element

Each `Modifier` element within the `DrugEffectModifierComponent` defines a single modification.

#### Attributes of `Modifier`

| Attribute        | Type    | Description