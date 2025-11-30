---
title: Kiekurakeppi Wand Configuration
category: scripts
---

# Kiekurakeppi Wand Configuration

This document details the configuration for the "Kiekurakeppi" wand in Noita, focusing on its visual and UI elements.

## Core Wand Properties

*   **Item Name:** `$item_wand_kiekurakeppi` (This is a localization key for the wand's name.)
*   **Sprite Path:** `data/items_gfx/wands/custom/wood_01.png` (Specifies the visual asset for the wand.)
*   **Sprite Offset X:** `3` (Horizontal adjustment for the sprite.)
*   **Sprite Offset Y:** `3` (Vertical adjustment for the sprite.)
*   **UI Sprite:** `data/items_gfx/wands/custom/wood_01.png` (The sprite used in the UI inventory.)
*   **Always Use Item Name in UI:** `true` (Ensures the wand's custom name is always displayed in the UI.)

## Scripting Context

This configuration is applied to an entity using `EntityGetFirstComponent` and `component_write` functions, targeting `SpriteComponent` and `ItemComponent` to modify the wand's appearance and how it's presented in the game's user interface.