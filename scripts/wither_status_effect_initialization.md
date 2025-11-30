---
title: Wither Status Effect Initialization
category: scripts
---

---

# Wither Status Effect Initialization

This script handles the initialization of the "wither" status effect on a player entity. It modifies the player's damage resistances and stores the original values for later restoration.

## Key Functionality

### Damage Resistance Modification

The primary function of this script is to increase the player's vulnerability to all damage types. It iterates through a predefined list of damage resistances and sets their multipliers to `1.2`, making the player take 20% more damage from each type.

### Storing Original Resistances

Before modifying the damage multipliers, the script reads and stores the original values. This is crucial for restoring the player's resistances when the wither effect is removed. The original resistance values are concatenated into a single string, separated by spaces, and stored in a `VariableStorageComponent` with the name `wither_data`.

### Disabling Effect Resistance Components

The script also iterates through all child entities of the player and disables any components tagged with `effect_resistance`. This is likely to prevent other status effects or resistances from interfering with the wither effect's intended impact.

## Key Attributes/Elements

| Attribute/Element        | Description