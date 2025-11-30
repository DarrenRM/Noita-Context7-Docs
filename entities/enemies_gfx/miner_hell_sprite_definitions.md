---
title: Miner Hell Sprite Definitions
category: entities/enemies_gfx
---

# Miner Hell Sprite Definitions

This document details the sprite and animation definitions for the "Miner Hell" enemy in Noita, as found in `miner_hell.xml`. This file is crucial for understanding how the enemy visually appears and behaves during various actions.

## Sprite Attributes

The main `<Sprite>` tag defines the core visual properties of the Miner Hell.

| Attribute        | Value                               | Description                                                                 |
| :--------------- | :---------------------------------- | :-------------------------------------------------------------------------- |
| `filename`       | `data/enemies_gfx/miner_hell.png`   | Path to the sprite sheet containing all animation frames.                   |
| `hotspots_filename` | `data/enemies_gfx/miner_hotspots.png` | Path to the sprite sheet defining specific interaction points (e.g., hands). |
| `offset_x`       | `7`                                 | Horizontal offset for the sprite's origin.                                  |
| `offset_y`       | `12`                                | Vertical offset for the sprite's origin.                                    |
| `default_animation` | `stand`                             | The animation to play by default when the enemy is idle.                    |

### Hotspots

The `<Hotspot>` tag defines specific points on the sprite that can be referenced by game logic.

| Attribute | Value     | Description                                     |
| :-------- | :-------- | :---------------------------------------------- |
| `color`   | `ff0000`  | Color of the hotspot (often used for debugging). |
| `name`    | `hand`    | Identifier for this hotspot (e.g., "hand").     |

## Animation Definitions

The `<RectAnimation>` tags define individual animations for the Miner Hell. Each animation consists of a sequence of frames from the sprite sheet.

### `stand` Animation

*   **Description:** The default idle animation for the Miner Hell.
*   **Frames:** 6
*   **Frame Size:** 18x16 pixels
*   **Frame Wait:** 0.15 seconds
*   **Frames Per Row:** 6
*   **Position in Sprite Sheet:** `pos_x="0"`, `pos_y="1"`

### `attack` Animation

*   **Description:** Animation for a melee attack.
*   **Frames:** 7
*   **Frame Size:** 18x16 pixels
*   **Frame Wait:** 0.04 seconds
*   **Frames Per Row:** 8
*   **Loop:** `0` (plays once)
*   **Position in Sprite Sheet:** `pos_x="0"`, `pos_y="17"`

#### Events within `attack`

| Frame | Event Name    | Description                                                              |
| :---- | :------------ | :----------------------------------------------------------------------- |
| 4     | `attack_melee` | Triggers a melee attack action.                                          |
| 4     | `voc_attack`  | Triggers a vocalization associated with attacking.                       |

### `attack_ranged` Animation

*   **Description:** Animation for a ranged attack (likely throwing something).
*   **Frames:** 7
*   **Frame Size:** 18x16 pixels
*   **Frame Wait:** 0.1 seconds
*   **Frames Per Row:** 8
*   **Loop:** `0` (plays once)
*   **Position in Sprite Sheet:** `pos_x="0"`, `pos_y="17"`

#### Events within `attack_ranged`

| Frame | Event Name | Description                               |
| :---- | :--------- | :---------------------------------------- |
| 4     | `throw`    | Triggers the throwing action.             |

### `walk` Animation

*   **Description:** Animation for the Miner Hell walking.
*   **Frames:** 6
*   **Frame Size:** 18x16 pixels
*   **Frame Wait:** 0.11 seconds
*   **Frames Per Row:** 6
*   **Position in Sprite Sheet:** `pos_x="0"`, `pos_y="33"`

#### Events within `walk`

| Frame | Event Name | Description                                                              |
| :---- | :--------- | :----------------------------------------------------------------------- |
| 2     | `step`     | Triggers a footstep sound/effect when walking.                           |
| 5     | `step`     | Triggers a footstep sound/effect when walking.                           |

### `run` Animation

*   **Description:** Animation for the Miner Hell running.
*   **Frames:** 6
*   **Frame Size:** 18x16 pixels
*   **Frame Wait:** 0.11 seconds
*   **Frames Per Row:** 8
*   **Position in Sprite Sheet:** `pos_x="0"`, `pos_y="33"`

#### Events within `run`

| Frame | Event Name | Description                                                              |
| :---- | :--------- | :----------------------------------------------------------------------- |
| 2     | `step`     | Triggers a footstep sound/effect when running.                           |
| 5     | `step`     | Triggers a footstep sound/effect when running.                           |

### `jump_up` Animation

*   **Description:** Animation for the Miner Hell jumping upwards.
*   **Frames:** 3
*   **Frame Size:** 18x16 pixels
*   **Frame Wait:** 0.07 seconds
*   **Frames Per Row:** 8
*   **Loop:** `0` (plays once)
*   **Position in Sprite Sheet:** `pos_x="0"`, `pos_y="49"`

#### Events within `jump_up`

| Frame | Event Name | Description                               |
| :---- | :--------- | :---------------------------------------- |
| 0     | `jump`     | Triggers the jump action.                 |

### `knockback` Animation

*   **Description:** Animation played when the Miner Hell is hit and knocked back.
*   **Frames:** 1
*   **Frame Size:** 18x16 pixels
*   **Frame Wait:** 0.11 seconds
*   **Frames Per Row:** 8
*   **Position in Sprite Sheet:** `pos_x="0"`, `pos_y="65"`

### `lower_head` Animation

*   **Description:** Animation for the Miner Hell lowering its head.
*   **Frames:** 1
*   **Frame Size:** 18x16 pixels
*   **Frame Wait:** 0.01 seconds
*   **Frames Per Row:** 8
*   **Loop:** `0` (plays once)
*   **Position in Sprite Sheet:** `pos_x="0"`, `pos_y="81"`

### `eat` Animation

*   **Description:** Animation for the Miner Hell eating.
*   **Frames:** 6
*   **Frame Size:** 18x16 pixels
*   **Frame Wait:** 0.058 seconds
*   **Frames Per Row:** 8
*   **Loop:** `0` (plays once)
*   **Position in Sprite Sheet:** `pos_x="0"`, `pos_y="81"`

#### Events within `eat`

| Frame | Event Name     | Description                                                              |
| :---- | :------------- | :----------------------------------------------------------------------- |
| 4     | `attack_stomp` | Triggers a stomp attack action.                                          |
| 0     | `voc_stomp`    | Triggers a vocalization associated with a stomp attack.                  |

### `raise_head` Animation

*   **Description:** Animation for the Miner Hell raising its head.
*   **Frames:** 1
*   **Frame Size:** 18x16 pixels
*   **Frame Wait:** 0.01 seconds
*   **Frames Per Row:** 8
*   **Loop:** `0` (plays once)
*   **Position in Sprite Sheet:** `pos_x="0"`, `pos_y="81"`

### `alert` Animation

*   **Description:** Animation played when the Miner Hell becomes alerted.
*   **Frames:** 2
*   **Frame Size:** 18x16 pixels
*   **Frame Wait:** 0.07 seconds
*   **Frames Per Row:** 8
*   **Loop:** `0` (plays once)
*   **Position in Sprite Sheet:** `pos_x="0"`, `pos_y="97"`

### `burn` Animation

*   **Description:** Animation for the Miner Hell being on fire.
*   **Frames:** 6
*   **Frame Size:** 18x16 pixels
*   **Frame Wait:** 0.08 seconds
*   **Frames Per Row:** 8
*   **Position in Sprite Sheet:** `pos_x="0"`, `pos_y="113"`

#### Events within `burn`

| Frame | Event Name | Description                                                              |
| :---- | :--------- | :----------------------------------------------------------------------- |
| 2     | `step`     | Triggers a footstep sound/effect (potentially indicating movement while burning). |
| 5     | `step`     | Triggers a footstep sound/effect (potentially indicating movement while burning). |

### `jump_fall` Animation

*   **Description:** Animation for the Miner Hell falling after a jump.
*   **Frames:** 3
*   **Frame Size:** 18x16 pixels
*   **Frame Wait:** 0.07 seconds
*   **Frames Per Row:** 8
*   **Loop:** `0` (plays once)
*   **Position in Sprite Sheet:** `pos_x="0"`, `pos_y="129"`

### `land` Animation

*   **Description:** Animation played when the Miner Hell lands after a jump.
*   **Frames:** 2
*   **Frame Size:** 18x16 pixels
*   **Frame Wait:** 0.06 seconds
*   **Frames Per Row:** 8
*   **Loop:** `0` (plays once)
*   **Position in Sprite Sheet:** `pos_x="0"`, `pos_y="145"`

### `swim_idle` Animation

*   **Description:** Idle animation when the Miner Hell is swimming.
*   **Frames:** 6
*   **Frame Size:** 18x16 pixels
*   **Frame Wait:** 0.065 seconds
*   **Frames Per Row:** 8
*   **Position in Sprite Sheet:** `pos_x="0"`, `pos_y="161"`

#### Events within `swim_idle`

| Frame | Event Name | Description                               |
| :---- | :--------- | :---------------------------------------- |
| 2     | `paddle`   | Triggers a swimming paddle action.        |
| 5     | `paddle`   | Triggers a swimming paddle action.        |

### `swim_move` Animation

*   **Description:** Animation for the Miner Hell moving while swimming.
*   **Frames:** 6
*   **Frame Size:** 18x16 pixels
*   **Frame Wait:** 0.06 seconds
*   **Frames Per Row:** 8
*   **Position in Sprite Sheet:** `pos_x="0"`, `pos_y="161"`

#### Events within `swim_move`

| Frame | Event Name | Description                               |
| :---- | :--------- | :---------------------------------------- |
| 2     | `paddle`   | Triggers a swimming paddle action.        |
| 5     | `paddle`   | Triggers a swimming paddle action.        |

### `jump_prepare` Animation

*   **Description:** Animation for preparing to jump.
*   **Frames:** 2
*   **Frame Size:** 18x16 pixels
*   **Frame Wait:** 0.06 seconds
*   **Frames Per Row:** 8
*   **Loop:** `0` (plays once)
*   **Position in Sprite Sheet:** `pos_x="0"`, `pos_y="177"`

#### Events within `jump_prepare`

| Frame | Event Name   | Description                               |
| :---- | :----------- | :---------------------------------------- |
| 0     | `voc_jump`   | Triggers a vocalization for jumping.      |
| 2     | `jump_start` | Triggers the start of the jump action.    |