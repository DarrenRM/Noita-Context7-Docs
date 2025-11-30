---
title: GodInfoComponent
source: https://noita.wiki.gg/wiki/Documentation:GodInfoComponent
category: modding-wiki
---

# GodInfoComponent

This documentation page details the `GodInfoComponent` in Noita, a crucial component for understanding and manipulating enemy AI behavior, specifically their "god" or "awareness" states. Modders can leverage this information to customize how enemies perceive the player, react to threats, and utilize their abilities, leading to more dynamic and challenging gameplay.

## Overview

The `GodInfoComponent` is attached to entities that possess a form of "god" or awareness state. This component governs how these entities perceive their environment and the player, influencing their decision-making and combat AI. Understanding its various parameters allows modders to fine-tune enemy detection ranges, reaction times, and overall threat assessment.

## Component Parameters

The `GodInfoComponent` has several key parameters that control its behavior. These are typically found within the entity's XML definition.

### Core Awareness Parameters

These parameters directly influence how the entity perceives the player and its surroundings.

| Parameter Name        | Type    | Description