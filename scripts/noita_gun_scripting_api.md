---
title: Noita Gun Scripting API
category: scripts
---

# Noita Gun Scripting API

This document outlines the core Lua functions and global variables used for defining and managing guns and their actions within Noita. It's intended to help AI models understand and generate modding content related to gun mechanics.

## Core Concepts

The gun system in Noita revolves around a deck of "actions" (cards) that are drawn, played, and managed. These actions can be projectiles, materials, or other effects. The system handles drawing, mana costs, reloading, and applying modifiers.

## Key Global Variables and Constants

These are essential for understanding the state and behavior of the gun system.

| Variable/Constant                 | Description