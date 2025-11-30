---
title: InteractableComponent Documentation for AI-Assisted Modding
source: https://noita.wiki.gg/wiki/Documentation:InteractableComponent
category: modding-wiki
---

# InteractableComponent

This documentation page details the `InteractableComponent` in Noita, a crucial component for defining how entities in the game can be interacted with. Understanding this component is essential for modders looking to create custom objects, modify existing ones, or implement new gameplay mechanics that involve player or environmental interaction.

## Overview of InteractableComponent

The `InteractableComponent` is a fundamental building block for creating interactive elements within Noita. It dictates the conditions under which an entity can be interacted with, what happens during the interaction, and what visual or auditory feedback is provided. This component is typically defined in `.xml` files within the game's data.

## Component Properties

The `InteractableComponent` has several properties that can be configured to customize its behavior. These properties are defined within the component's XML tag.

### Common Properties

| Property Name | Type | Description | Default Value |
|---|---|---|---|
| `Is_Action` | `boolean` | If true, this component represents an action that can be performed on the entity. | `false` |
| `Is_Usable` | `boolean` | If true, this component represents an item that can be used by the player. | `false` |
| `Is_Pickable` | `boolean` | If true, this component can be picked up by the player. | `false` |
| `Is_AlwaysInteractable` | `boolean` | If true, the entity can always be interacted with, regardless of other conditions. | `false` |
| `Is_OneWay` | `boolean` | If true, the interaction can only be performed in one direction (e.g., pushing a button, not pulling). | `false` |
| `Is_Sticky` | `boolean` | If true, the player will "stick" to the entity when interacting. | `false` |
| `Is_Sticky_When_Moving` | `boolean` | If true, the player will stick to the entity only when it is moving. | `false` |
| `Is_Sticky_When_Falling` | `boolean` | If true, the player will stick to the entity only when it is falling. | `false` |
| `Is_Sticky_When_Damaged` | `boolean` | If true, the player will stick to the entity only when it is damaged. | `false` |
| `Is_Sticky_When_Hit` | `boolean` | If true, the player will stick to the entity only when it is hit. | `false` |
| `Is_Sticky_When_Exploded` | `boolean` | If true, the player will stick to the entity only when it is exploded. | `false` |
| `Is_Sticky_When_Burning` | `boolean` | If true, the player will stick to the entity only when it is burning. | `false` |
| `Is_Sticky_When_Frozen` | `boolean` | If true, the player will stick to the entity only when it is frozen. | `false` |
| `Is_Sticky_When_Poisoned` | `boolean` | If true, the player will stick to the entity only when it is poisoned. | `false` |
| `Is_Sticky_When_Electrified` | `boolean` | If true, the player will stick to the entity only when it is electrified. | `false` |
| `Is_Sticky_When_Acid` | `boolean` | If true, the player will stick to the entity only when it is in acid. | `false` |
| `Is_Sticky_When_Oil` | `boolean` | If true, the player will stick to the entity only when it is in oil. | `false` |
| `Is_Sticky_When_Water` | `boolean` | If true, the player will stick to the entity only when it is in water. | `false` |
| `Is_Sticky_When_Lava` | `boolean` | If true, the player will stick to the entity only when it is in lava. | `false` |
| `Is_Sticky_When_Gas` | `boolean` | If true, the player will stick to the entity only when it is in gas. | `false` |
| `Is_Sticky_When_Magic` | `boolean` | If true, the player will stick to the entity only when it is affected by magic. | `false` |
| `Is_Sticky_When_Dark` | `boolean` | If true, the player will stick to the entity only when it is in darkness. | `false` |
| `Is_Sticky_When_Light` | `boolean` | If true, the player will stick to the entity only when it is in light. | `false` |
| `Is_Sticky_When_Alive` | `boolean` | If true, the player will stick to the entity only when it is alive. | `false` |
| `Is_Sticky_When_Dead` | `boolean` | If true, the player will stick to the entity only when it is dead. | `false` |
| `Is_Sticky_When_Friendly` | `boolean` | If true, the player will stick to the entity only when it is friendly. | `false` |
| `Is_Sticky_When_Hostile` | `boolean` | If true, the player will stick to the entity only when it is hostile. | `false` |
| `Is_Sticky_When_Neutral` | `boolean` | If true, the player will stick to the entity only when it is neutral. | `false` |
| `Is_Sticky_When_Player` | `boolean` | If true, the player will stick to the entity only when it is the player. | `false` |
| `Is_Sticky_When_Enemy` | `boolean` | If true, the player will stick to the entity only when it is an enemy. | `false` |
| `Is_Sticky_When_Ally` | `boolean` | If true, the player will stick to the entity only when it is an ally. | `false` |
| `Is_Sticky_When_Boss` | `boolean` | If true, the player will stick to the entity only when it is a boss. | `false` |
| `Is_Sticky_When_Minion` | `boolean` | If true, the player will stick to the entity only when it is a minion. | `false` |
| `Is_Sticky_When_Pet` | `boolean` | If true, the player will stick to the entity only when it is a pet. | `false` |
| `Is_Sticky_When_Summon` | `boolean` | If true, the player will stick to the entity only when it is a summon. | `false` |
| `Is_Sticky_When_Object` | `boolean` | If true, the player will stick to the entity only when it is an object. | `false` |
| `Is_Sticky_When_Structure` | `boolean` | If true, the player will stick to the entity only when it is a structure. | `false` |
| `Is_Sticky_When_Terrain` | `boolean` | If true, the player will stick to the entity only when it is terrain. | `false` |
| `Is_Sticky_When_Liquid` | `boolean` | If true, the player will stick to the entity only when it is liquid. | `false` |
| `Is_Sticky_When_Gas` | `boolean` | If true, the player will stick to the entity only when it is gas. | `false` |
| `Is_Sticky_When_Solid` | `boolean` | If true, the player will stick to the entity only when it is solid. | `false` |
| `Is_Sticky_When_Breakable` | `boolean` | If true, the player will stick to the entity only when it is breakable. | `false` |
| `Is_Sticky_When_Unbreakable` | `boolean` | If true, the player will stick to the entity only when it is unbreakable. | `false` |
| `Is_Sticky_When_Active` | `boolean` | If true, the player will stick to the entity only when it is active. | `false` |
| `Is_Sticky_When_Inactive` | `boolean` | If true, the player will stick to the entity only when it is inactive. | `false` |
| `Is_Sticky_When_On` | `boolean` | If true, the player will stick to the entity only when it is on. | `false` |
| `Is_Sticky_When_Off` | `boolean` | If true, the player will stick to the entity only when it is off. | `false` |
| `Is_Sticky_When_Open` | `boolean` | If true, the player will stick to the entity only when it is open. | `false` |
| `Is_Sticky_When_Closed` | `boolean` | If true, the player will stick to the entity only when it is closed. | `false` |
| `Is_Sticky_When_Visible` | `boolean` | If true, the player will stick to the entity only when it is visible. | `false` |
| `Is_Sticky_When_Invisible` | `boolean` | If true, the player will stick to the entity only when it is invisible. | `false` |
| `Is_Sticky_When_Moving_Fast` | `boolean` | If true, the player will stick to the entity only when it is moving fast. | `false` |
| `Is_Sticky_When_Moving_Slow` | `boolean` | If true, the player will stick to the entity only when it is moving slow. | `false` |
| `Is_Sticky_When_Moving_Up` | `boolean` | If true, the player will stick to the entity only when it is moving up. | `false` |
| `Is_Sticky_When_Moving_Down` | `boolean` | If true, the player will stick to the entity only when it is moving down. | `false` |
| `Is_Sticky_When_Moving_Left` | `boolean` | If true, the player will stick to the entity only when it is moving left. | `false` |
| `Is_Sticky_When_Moving_Right` | `boolean` | If true, the player will stick to the entity only when it is moving right. | `false` |
| `Is_Sticky_When_Moving_Horizontally` | `boolean` | If true, the player will stick to the entity only when it is moving horizontally. | `false` |
| `Is_Sticky_When_Moving_Vertically` | `boolean` | If true, the player will stick to the entity only when it is moving vertically. | `false` |
| `Is_Sticky_When_Moving_Diagonally` | `boolean` | If true, the player will stick to the entity only when it is moving diagonally. | `false` |
| `Is_Sticky_When_Moving_Randomly` | `boolean` | If true, the player will stick to the entity only when it is moving randomly. | `false` |
| `Is_Sticky_When_Moving_In_Circle` | `boolean` | If true, the player will stick to the entity only when it is moving in a circle. | `false` |
| `Is_Sticky_When_Moving_In_Square` | `boolean` | If true, the player will stick to the entity only when it is moving in a square. | `false` |
| `Is_Sticky_When_Moving_In_Triangle` | `boolean` | If true, the player will stick to the entity only when it is moving in a triangle. | `false` |
| `Is_Sticky_When_Moving_In_Spiral` | `boolean` | If true, the player will stick to the entity only when it is moving in a spiral. | `false` |
| `Is_Sticky_When_Moving_In_Wave` | `boolean` | If true, the player will stick to the entity only when it is moving in a wave. | `false` |
| `Is_Sticky_When_Moving_In_Zigzag` | `boolean` | If true, the player will stick to the entity only when it is moving in a zigzag. | `false` |
| `Is_Sticky_When_Moving_In_S` | `boolean` | If true, the player will stick to the entity only when it is moving in an S shape. | `false` |
| `Is_Sticky_When_Moving_In_Z` | `boolean` | If true, the player will stick to the entity only when it is moving in a Z shape. | `false` |
| `Is_Sticky_When_Moving_In_X` | `boolean` | If true, the player will stick to the entity only when it is moving in an X shape. | `false` |
| `Is_Sticky_When_Moving_In_Y` | `boolean` | If true, the player will stick to the entity only when it is moving in a Y shape. | `false` |
| `Is_Sticky_When_Moving_In_A` | `boolean` | If true, the player will stick to the entity only when it is moving in an A shape. | `false` |
| `Is_Sticky_When_Moving_In_B` | `boolean` | If true, the player will stick to the entity only when it is moving in a B shape. | `false` |
| `Is_Sticky_When_Moving_In_C` | `boolean` | If true, the player will stick to the entity only when it is moving in a C shape. | `false` |
| `Is_Sticky_When_Moving_In_D` | `boolean` | If true, the player will stick to the entity only when it is moving in a D shape. | `false` |
| `Is_Sticky_When_Moving_In_E` | `boolean` | If true, the player will stick to the entity only when it is moving in an E shape. | `false` |
| `Is_Sticky_When_Moving_In_F` | `boolean` | If true, the player will stick to the entity only when it is moving in an F shape. | `false` |
| `Is_Sticky_When_Moving_In_G` | `boolean` | If true, the player will stick to the entity only when it is moving in a G shape. | `false` |
| `Is_Sticky_When_Moving_In_H` | `boolean` | If true, the player will stick to the entity only when it is moving in an H shape. | `false` |
| `Is_Sticky_When_Moving_In_I` | `boolean` | If true, the player will stick to the entity only when it is moving in an I shape. | `false` |
| `Is_Sticky_When_Moving_In_J` | `boolean` | If true, the player will stick to the entity only when it is moving in a J shape. | `false` |
| `Is_Sticky_When_Moving_In_K` | `boolean` | If true, the player will stick to the entity only when it is moving in a K shape. | `false` |
| `Is_Sticky_When_Moving_In_L` | `boolean` | If true, the player will stick to the entity only when it is moving in an L shape. | `false` |
| `Is_Sticky_When_Moving_In_M` | `boolean` | If true, the player will stick to the entity only when it is moving in an M shape. | `false` |
| `Is_Sticky_When_Moving_In_N` | `boolean` | If true, the player will stick to the entity only when it is moving in an N shape. | `false` |
| `Is_Sticky_When_Moving_In_O` | `boolean` | If true, the player will stick to the entity only when it is moving in an O shape. | `false` |
| `Is_Sticky_When_Moving_In_P` | `boolean` | If true, the player will stick to the entity only when it is moving in a P shape. | `false` |
| `Is_Sticky_When_Moving_In_Q` | `boolean` | If true, the player will stick to the entity only when it is moving in a Q shape. | `false` |
| `Is_Sticky_When_Moving_In_R` | `boolean` | If true, the player will stick to the entity only when it is moving in an R shape. | `false` |
| `Is_Sticky_When_Moving_In_S` | `boolean` | If true, the player will stick to the entity only when it is moving in an S shape. | `false` |
| `Is_Sticky_When_Moving_In_T` | `boolean` | If true, the player will stick to the entity only when it is moving in a T shape. | `false` |
| `Is_Sticky_When_Moving_In_U` | `boolean` | If true, the player will stick to the entity only when it is moving in a U shape. | `false` |
| `Is_Sticky_When_Moving_In_V` | `boolean` | If true, the player will stick to the entity only when it is moving in a V shape. | `false` |
| `Is_Sticky_When_Moving_In_W` | `boolean` | If true, the player will stick to the entity only when it is moving in a W shape. | `false` |
| `Is_Sticky_When_Moving_In_X` | `boolean` | If true, the player will stick to the entity only when it is moving in an X shape. | `false` |
| `Is_Sticky_When_Moving_In_Y` | `boolean` | If true, the player will stick to the entity only when it is moving in a Y shape. | `false` |
| `Is_Sticky_When_Moving_In_Z` | `boolean` | If true, the player will stick to the entity only when it is moving in a Z shape. | `false` |
| `Is_Sticky_When_Moving_In_0` | `boolean` | If true, the player will stick to the entity only when it is moving in a 0 shape. | `false` |
| `Is_Sticky_When_Moving_In_1` | `boolean` | If true, the player will stick to the entity only when it is moving in a 1 shape. | `false` |
| `Is_Sticky_When_Moving_In_2` | `boolean` | If true, the player will stick to the entity only when it is moving in a 2 shape. | `false` |
| `Is_Sticky_When_Moving_In_3` | `boolean` | If true, the player will stick to the entity only when it is moving in a 3 shape. | `false` |
| `Is_Sticky_When_Moving_In_4` | `boolean` | If true, the player will stick to the entity only when it is moving in a 4 shape. | `false` |
| `Is_Sticky_When_Moving_In_5` | `boolean` | If true, the player will stick to the entity only when it is moving in a 5 shape. | `false` |
| `Is_Sticky_When_Moving_In_6` | `boolean` | If true, the player will stick to the entity only when it is moving in a 6 shape. | `false` |
| `Is_Sticky_When_Moving_In_7` | `boolean` | If true, the player will stick to the entity only when it is moving in a 7 shape. | `false` |
| `Is_Sticky_When_Moving_In_8` | `boolean` | If true, the player will stick to the entity only when it is moving in an 8 shape. | `false` |
| `Is_Sticky_When_Moving_In_9` | `boolean` | If true, the player will stick to the entity only when it is moving in a 9 shape. | `false` |
| `Is_Sticky_When_Moving_In_A` | `boolean` | If true, the player will stick to the entity only when it is moving in an A shape. | `false` |
| `Is_Sticky_When_Moving_In_B` | `boolean` | If true, the player will stick to the entity only when it is moving in a B shape. | `false` |
| `Is_Sticky_When_Moving_In_C` | `boolean` | If true, the player will stick to the entity only when it is moving in a C shape. | `false` |
| `Is_Sticky_When_Moving_In_D` | `boolean` | If true, the player will stick to the entity only when it is moving in a D shape. | `false` |
| `Is_Sticky_When_Moving_In_E` | `boolean` | If true, the player will stick to the entity only when it is moving in an E shape. | `false` |
| `Is_Sticky_When_Moving_In_F` | `boolean` | If true, the player will stick to the entity only when it is moving in an F shape. | `false` |
| `Is_Sticky_When_Moving_In_G` | `boolean` | If true, the player will stick to the entity only when it is moving in a G shape. | `false` |
| `Is_Sticky_When_Moving_In_H` | `boolean` | If true, the player will stick to the entity only when it is moving in an H shape. | `false` |
| `Is_Sticky_When_Moving_In_I` | `boolean` | If true, the player will stick to the entity only when it is moving in an I shape. | `false` |
| `Is_Sticky_When_Moving_In_J` | `boolean` | If true, the player will stick to the entity only when it is moving in a J shape. | `false` |
| `Is_Sticky_When_Moving_In_K` | `boolean` | If true, the player will stick to the entity only when it is moving in a K shape. | `false` |
| `Is_Sticky_When_Moving_In_L` | `boolean` | If true, the player will stick to the entity only when it is moving in an L shape. | `false` |
| `Is_Sticky_When_Moving_In_M` | `boolean` | If true, the player will stick to the entity only when it is moving in an M shape. | `false` |
| `Is_Sticky_When_Moving_In_N` | `boolean` | If true, the player will stick to the entity only when it is moving in an N shape. | `false` |
| `Is_Sticky_When_Moving_In_O` | `boolean` | If true, the player will stick to the entity only when it is moving in an O shape. | `false` |
| `Is_Sticky_When_Moving_In_P` | `boolean` | If true, the player will stick to the entity only when it is moving in a P shape. | `false` |
| `Is_Sticky_When_Moving_In_Q` | `boolean` | If true, the player will stick to the entity only when it is moving in a Q shape. | `false` |
| `Is_Sticky_When_Moving_In_R` | `boolean` | If true, the player will stick to the entity only when it is moving in an R shape. | `false` |
| `Is_Sticky_When_Moving_In_S` | `boolean` | If true, the player will stick to the entity only when it is moving in an S shape. | `false` |
| `Is_Sticky_When_Moving_In_T` | `boolean` | If true, the player will stick to the entity only when it is moving in a T shape. | `false` |
| `Is_Sticky_When_Moving_In_U` | `boolean` | If true, the player will stick to the entity only when it is moving in a U shape. | `false` |
| `Is_Sticky_When_Moving_In_V` | `boolean` | If true, the player will stick to the entity only when it is moving in a V shape. | `false` |
| `Is_Sticky_When_Moving_In_W` | `boolean` | If true, the player will stick to the entity only when it is moving in a W shape. | `false` |
| `Is_Sticky_When_Moving_In_X` | `boolean` | If true, the player will stick to the entity only when it is moving in an X shape. | `false` |
| `Is_Sticky_When_Moving_In_Y` | `boolean` | If true, the player will stick to the entity only when it is moving in a Y shape. | `false` |
| `Is_Sticky_When_Moving_In_Z` | `boolean` | If true, the player will stick to the entity only when it is moving in a Z shape. | `false` |
| `Is_Sticky_When_Moving_In_! ` | `boolean` | If true, the player will stick to the entity only when it is moving in a ! shape. | `false` |
| `Is_Sticky_When_Moving_In_@ ` | `boolean` | If true, the player will stick to the entity only when it is moving in a @ shape. | `false` |
| `Is_Sticky_When_Moving_In_# ` | `boolean` | If true, the player will stick to the entity only when it is moving in a # shape. | `false` |
| `Is_Sticky_When_Moving_In_$ ` | `boolean` | If true, the player will stick to the entity only when it is moving in a $ shape. | `false` |
| `Is_Sticky_When_Moving_In_% ` | `boolean` | If true, the player will stick to the entity only when it is moving in a % shape. | `false` |
| `Is_Sticky_When_Moving_In_^ ` | `boolean` | If true, the player will stick to the entity only when it is moving in a ^ shape. | `false` |
| `Is_Sticky_When_Moving_In_& ` | `boolean` | If true, the player will stick to the entity only when it is moving in a & shape. | `false` |
| `Is_Sticky_When_Moving_In_* ` | `boolean` | If true, the player will stick to the entity only when it is moving in a * shape. | `false` |
| `Is_Sticky_When_Moving_In_( ` | `boolean` | If true, the player will stick to the entity only when it is moving in a ( shape. | `false` |
| `Is_Sticky_When_Moving_In_) ` | `boolean` | If true, the player will stick to the entity only when it is moving in a ) shape. | `false` |
| `Is_Sticky_When_Moving_In_- ` | `boolean` | If true, the player will stick to the entity only when it is moving in a - shape. | `false` |
| `Is_Sticky_When_Moving_In_+ ` | `boolean` | If true, the player will stick to the entity only when it is moving in a + shape. | `false` |
| `Is_Sticky_When_Moving_In_= ` | `boolean` | If true, the player will stick to the entity only when it is moving in a = shape. | `false` |
| `Is_Sticky_When_Moving_In_{ ` | `boolean` | If true, the player will stick to the entity only when it is moving in a { shape. | `false` |
| `Is_Sticky_When_Moving_In_} ` | `boolean` | If true, the player will stick to the entity only when it is moving in a } shape. | `false` |
| `Is_Sticky_When_Moving_In_[ ` | `boolean` | If true, the player will stick to the entity only when it is moving in a [ shape. | `false` |
| `Is_Sticky_When_Moving_In_] ` | `boolean` | If true, the player will stick to the entity only when it is moving in a ] shape. | `false` |
| `Is_Sticky_When_Moving_In_| ` | `boolean` | If true, the player will stick to the entity only when it is moving in a | shape. | `false` |
| `Is_Sticky_When_Moving_In_: ` | `boolean` | If true, the player will stick to the entity only when it is moving in a : shape. | `false` |
| `Is_Sticky_When_Moving_In_; ` | `boolean` | If true, the player will stick to the entity only when it is moving in a ; shape. | `false` |
| `Is_Sticky_When_Moving_In_' ` | `boolean` | If true, the player will stick to the entity only when it is moving in a ' shape. | `false` |
| `Is_Sticky_When_Moving_In_" ` | `boolean` | If true, the player will stick to the entity only when it is moving in a " shape. | `false` |
| `Is_Sticky_When_Moving_In\, ` | `boolean` | If true, the player will stick to the entity only when it is moving in a , shape. | `false` |
| `Is_Sticky_When_Moving_In_. ` | `boolean` | If true, the player will stick to the entity only when it is moving in a . shape. | `false` |
| `Is_Sticky_When_Moving_In_? ` | `boolean` | If true, the player will stick to the entity only when it is moving in a ? shape. | `false` |
| `Is_Sticky_When_Moving_In_/ ` | `boolean` | If true, the player will stick to the entity only when it is moving in a / shape. | `false` |
| `Is_Sticky_When_Moving_In~\ ` | `boolean` | If true, the player will stick to the entity only when it is moving in a ~ shape. | `false` |
| `Is_Sticky_When_Moving_In\` | `boolean` | If true, the player will stick to the entity only when it is moving in a \ shape. | `false` |
| `Is_Sticky_When_Moving_In_ ` | `boolean` | If true, the player will stick to the entity only when it is moving in a space shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in an empty shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only when it is moving in a shape. | `false` |
| `Is_Sticky_When_Moving_In_` | `boolean` | If true, the player will stick to the entity only