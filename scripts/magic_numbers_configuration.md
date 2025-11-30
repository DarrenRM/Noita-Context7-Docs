---
title: Magic Numbers Configuration
category: data
---

# Magic Numbers Configuration

This document outlines key magic numbers used in Noita's game logic, affecting various aspects of gameplay, rendering, audio, and UI. These values can be modified to alter game behavior.

## Design & Gameplay Settings

These numbers control fundamental game design choices and player interactions.

### Core Game Mechanics

| Attribute Name                      | Description                                                              | Value |
| :---------------------------------- | :----------------------------------------------------------------------- | :---- |
| `DESIGN_DAILY_RANDOM_STARTING_ITEMS` | Enables random starting items for daily runs.                            | `1`   |
| `DESIGN_MATERIAL_INGESTION_STATUS_FX` | Controls whether status effects are applied when ingesting materials.    | `1`   |
| `DESIGN_DAY_CYCLE_SPEED`            | Determines the speed of the in-game day/night cycle.                     | `0.0015` |
| `DESIGN_SPELL_VISUALIZER`           | Enables or disables the spell visualizer.                                | `1`   |
| `DESIGN_PLAYER_START_POS_X`         | The starting X-coordinate for the player.                                | `227` |
| `DESIGN_PLAYER_START_POS_Y`         | The starting Y-coordinate for the player.                                | `-85` |

### Drop Rates

These values influence the probability of dropping items of different tiers.

| Attribute Name | Description                               | Value |
| :------------- | :---------------------------------------- | :---- |
| `DROP_LEVEL_1` | Drop chance for level 1 items.            | `3.78` |
| `DROP_LEVEL_2` | Drop chance for level 2 items.            | `2.0`  |
| `DROP_LEVEL_3` | Drop chance for level 3 items.            | `0.9`  |
| `DROP_LEVEL_4` | Drop chance for level 4 items.            | `0.6`  |
| `DROP_LEVEL_5` | Drop chance for level 5 items.            | `0.4`  |
| `DROP_LEVEL_6` | Drop chance for level 6 items.            | `0.3`  |
| `DROP_LEVEL_7` | Drop chance for level 7 items.            | `0.27` |
| `DROP_LEVEL_8` | Drop chance for level 8 items.            | `0.26` |
| `DROP_LEVEL_9` | Drop chance for level 9 items.            | `0.25` |

### Game Effects

| Attribute Name                               | Description                                                              | Value |
| :------------------------------------------- | :----------------------------------------------------------------------- | :---- |
| `GAMEEFFECT_GLOBAL_GORE_GORE_MULTIPLIER`     | Multiplier for global gore effects.                                      | `5`   |
| `GAMEEFFECT_CRITICAL_HIT_BOOST_CRIT_EXTRA_CHANCE` | Additional chance for critical hits.                                     | `10`  |
| `GAMEEFFECT_EXTRA_MONEY_TRICK_KILL_MULTIPLIER` | Multiplier for money gained from trick kills.                            | `2`   |
| `GAMEEFFECT_MOVEMENT_FASTER_SPEED_MULTIPLIER` | General speed multiplier for faster movement effects.                    | `1.5` |
| `GAMEEFFECT_FIRE_MOVEMENT_SPEED_MULTIPLIER`  | Speed multiplier when affected by fire.                                  | `1.15` |
| `GAMEEFFECT_MANA_REGENERATION_SPEED_MULTIPLIER` | Multiplier for mana regeneration speed.                                  | `3`   |

### Physics & Ragdoll

| Attribute Name                      | Description                                                              | Value |
| :---------------------------------- | :----------------------------------------------------------------------- | :---- |
| `PHYSICS_FLOATER_FORCE_COEFF`       | Coefficient for floater force.                                           | `15.0` |
| `PHYSICS_RAGDOLL_VERY_STIFF_JOINT_STIFFNESS` | Stiffness of very stiff joints in ragdoll physics.                       | `2`   |
| `PHYSICS_JOINT_MAX_FORCE_MULTIPLIER` | Multiplier for maximum joint force.                                      | `160` |
| `RAGDOLL_OWN_VELOCITY_IMPULSE_MULTIPLIER` | Multiplier for impulse applied to ragdolls based on their own velocity. | `3`   |

### Player & Character

| Attribute Name                      | Description                                                              | Value |
| :---------------------------------- | :----------------------------------------------------------------------- | :---- |
| `PLAYER_KICK_FORCE`                 | The force applied when kicking.                                          | `50`  |
| `PLAYER_USE_NEW_JETPACK`            | Enables or disables the new jetpack implementation.                      | `0`   |
| `PLAYER_FAST_MOVEMENT_EXPLOSION_COOLDOWN` | Cooldown for fast movement explosions.                                   | `90`  |

## Camera Settings

These values control the behavior and appearance of the game camera.

### Camera Movement & Interpolation

| Attribute Name                      | Description                                                              | Value |
| :---------------------------------- | :----------------------------------------------------------------------- | :---- |
| `CAMERA_MOUSE_INTERPOLATION_SPEED`  | Speed at which the camera interpolates towards the mouse position.       | `0.25` |
| `CAMERA_POSITION_INTERPOLATION_SPEED` | Speed at which the camera interpolates to its target position.           | `3.52` |
| `CAMERA_DISTANCE_INTERPOLATION_SPEED` | Speed at which the camera interpolates its distance.                     | `1.16` |
| `CAMERA_GAMEPAD_INTERPOLATION_SPEED` | Speed at which the camera interpolates when using a gamepad.             | `1.75` |
| `CAMERA_RECOIL_AMOUNT`              | The magnitude of camera recoil.                                          | `1`   |
| `CAMERA_RECOIL_RELEASE_SPEED`       | How quickly camera recoil returns to its normal position.                | `15`  |

### Error Correction & Smoothing

| Attribute Name                      | Description                                                              | Value |
| :---------------------------------- | :----------------------------------------------------------------------- | :---- |
| `CAMERA_ERROR_CORRECTION_AMOUNT_X`  | Amount of X-axis error correction.                                       | `1.1` |
| `CAMERA_ERROR_CORRECTION_SPD_UP_Y`  | Speed of Y-axis error correction when moving up.                         | `0.935` |
| `CAMERA_ERROR_SMOOTHING_THRESHOLD_X` | Threshold for X-axis error smoothing.                                    | `10`  |
| `MULTIPLAYER_CAMERA_SMOOTHING`      | Smoothing factor for multiplayer camera.                                 | `0.25` |

## Rendering & Visuals

These settings affect how the game world is rendered and visual effects are displayed.

### Visual Effects

| Attribute Name                      | Description                                                              | Value |
| :---------------------------------- | :----------------------------------------------------------------------- | :---- |
| `DRAW_PARALLAX_BACKGROUND`          | Enables or disables parallax background rendering.                       | `1`   |
| `EXPLOSION_FACTORY_GORE_FX_PROBABLITY` | Probability of gore effects appearing from explosions.                   | `60`  |
| `EXPLOSION_FACTORY_STAIN_PERCENTAGE` | Percentage of explosion area that will be covered in stains.             | `0.4` |
| `RENDER_FIRE_GRAVITY`               | Gravity applied to fire particles.                                       | `-160` |
| `RENDER_FIRE_LIFETIME_MAX`          | Maximum lifetime of fire particles.                                      | `30`  |
| `RENDER_FIRE_HI_SCALE`              | Scale of high-intensity fire particles.                                  | `0.15` |
| `RENDER_PARALLAX_BACKGROUND_SHADER_GRADIENT` | Enables or disables shader gradients for parallax backgrounds.           | `1`   |

### UI Rendering

| Attribute Name                      | Description                                                              | Value |
| :---------------------------------- | :----------------------------------------------------------------------- | :---- |
| `UI_WOBBLE_AMOUNT_DEGREES`          | The amount of wobble applied to UI elements in degrees.                  | `3`   |
| `UI_SCALE_IN_SPEED`                 | Speed at which UI elements scale in.                                     | `0.2` |
| `UI_LOW_HP_THRESHOLD`               | The health threshold below which low HP warnings are triggered.          | `1.3333` |
| `UI_HEALTHBAR_Y_SPACING`            | Vertical spacing between health bars.                                    | `24`  |

## Audio Settings

These values control various audio aspects of the game.

### Sound Effects & Music

| Attribute Name                      | Description                                                              | Value |
| :---------------------------------- | :----------------------------------------------------------------------- | :---- |
| `AUDIO_GAMEEFFECT_FIRE_WEIGHT`      | Weight of fire sound effects.                                            | `0.1` |
| `AUDIO_MUSIC_VOLUME_DEFAULT`        | Default volume for music.                                                | `0.8` |
| `AUDIO_MUSIC_ACTION_FADE_UP_SPEED`  | Speed at which music fades up during action.                             | `0.1` |
| `AUDIO_COLLISION_SPEED_MULTIPLIER`  | Multiplier for collision sound effect intensity based on speed.          | `0.01` |
| `AUDIO_EXPLOSION_NO_SOUND_BELOW_RADIUS` | Radius below which explosion sounds are not played.                      | `2.05` |
| `AUDIO_CREDITS_TRACK_NAME`          | The name of the audio track used for credits.                            | `music/credits/03` |

## Other Settings

This section covers miscellaneous settings not categorized above.

### Biome & Pathfinding

| Attribute Name                      | Description                                                              | Value |
| :---------------------------------- | :----------------------------------------------------------------------- | :---- |
| `BIOME_APPARITION_CHANCE`           | Chance for a biome to appear.                                            | `30`  |
| `BIOME_MAP`                         | Path to the biome map script.                                            | `data/scripts/biome_map.lua` |
| `PATHFINDING_DISTANCE_FIELD_ENABLED` | Enables or disables the distance field for pathfinding.                  | `1`   |

### Inventory & UI Layout

| Attribute Name                      | Description                                                              | Value |
| :---------------------------------- | :----------------------------------------------------------------------- | :---- |
| `INVENTORY_ICON_SIZE`               | Size of inventory icons.                                                 | `20`  |
| `INVENTORY_STASH_X`                 | X-coordinate for the inventory stash.                                    | `370` |
| `UI_FULL_INVENTORY_OFFSET_X`        | Horizontal offset for the full inventory UI.                             | `170` |
| `UI_GAMEOVER_SCREEN_BOX_FROM_BOTTOM_PERCENT` | Percentage from the bottom for the game over screen box.                 | `12`  |

### Performance & Virtual Resolution

| Attribute Name                      | Description                                                              | Value |
| :---------------------------------- | :----------------------------------------------------------------------- | :---- |
| `USE_CUSTOM_THREADPOOL`             | Enables or disables a custom thread pool for performance.                | `1`   |
| `VIRTUAL_RESOLUTION_X`              | The virtual resolution width.                                            | `427` |
| `VIRTUAL_RESOLUTION_Y`              | The virtual resolution height.                                           | `242` |