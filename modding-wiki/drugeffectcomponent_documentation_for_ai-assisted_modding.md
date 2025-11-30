---
title: DrugEffectComponent Documentation for AI-Assisted Modding
source: https://noita.wiki.gg/wiki/Documentation:DrugEffectComponent
category: modding-wiki
---

# DrugEffectComponent Documentation

This document details the `DrugEffectComponent` in Noita, a crucial component for defining and managing status effects applied to entities. Understanding this component is essential for modders looking to create custom buffs, debuffs, and unique gameplay mechanics that alter entity behavior over time.

## Understanding DrugEffectComponent

The `DrugEffectComponent` is responsible for defining the properties and behaviors of various "drug" or status effects within Noita. These effects can range from simple stat changes to complex, timed alterations of an entity's capabilities.

### Core Functionality

This component allows modders to specify:

*   **Effect Type:** What kind of effect is being applied (e.g., healing, damage over time, stat modification).
*   **Duration:** How long the effect lasts.
*   **Magnitude:** The strength or intensity of the effect.
*   **Application Conditions:** When and how the effect is applied.
*   **Visual/Auditory Cues:** Any associated particle effects, sounds, or visual indicators.

### Key Parameters

The `DrugEffectComponent` utilizes several key parameters within its XML definition.

#### `effect`

This parameter defines the primary effect of the drug. It can take various values, often referencing other components or predefined effect types.

| Value           | Description