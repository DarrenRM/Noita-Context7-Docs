---
title: IKLimbsAnimatorComponent
source: https://noita.wiki.gg/wiki/Documentation:IKLimbsAnimatorComponent
category: modding-wiki
---

# IKLimbsAnimatorComponent

This documentation page details the `IKLimbsAnimatorComponent` in Noita, a crucial component for creating and managing Inverse Kinematics (IK) for character limbs. Understanding this component is essential for modders looking to implement custom animations, unique character movements, or dynamic limb behaviors that react to the game world.

## Overview

The `IKLimbsAnimatorComponent` is responsible for handling the Inverse Kinematics calculations that drive the animation of character limbs. This allows for more natural and responsive movement, where limb positions can be adjusted based on target points or environmental interactions. Modders can leverage this component to create sophisticated animations that go beyond simple pre-defined sequences.

## Component Properties

The `IKLimbsAnimatorComponent` has several properties that can be configured to control its behavior. These properties are typically defined within an entity's XML definition.

### `ik_limb_animator`

This is the primary tag for the IK Limbs Animator component.

| Property        | Type    | Description