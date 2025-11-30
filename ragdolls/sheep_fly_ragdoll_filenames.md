---
title: Sheep Fly Ragdoll Filenames
category: ragdolls
---

```

# Sheep Fly Ragdoll Filenames

This document lists the image filenames used for the "Sheep Fly" ragdoll in Noita. These files define the visual components of the ragdoll's body parts.

## Ragdoll Components

The following files represent the individual sprite pieces that make up the Sheep Fly ragdoll.

| Part Name     | Filename                     | Description                               |
|---------------|------------------------------|-------------------------------------------|
| Head          | `head.png`                   | The head sprite of the Sheep Fly.         |
| Right Torso   | `right_torso.png`            | The right side of the Sheep Fly's torso.  |
| Left Torso    | `left_torso.png`             | The left side of the Sheep Fly's torso.   |
| Left Front Leg| `left_frontleg.png`          | The left front leg sprite.                |
| Right Front Leg| `right_frontleg.png`         | The right front leg sprite.               |
| Left Hind Leg | `left_hindleg.png`           | The left hind leg sprite.                 |
| Right Hind Leg| `right_hindleg.png`          | The right hind leg sprite.                |
| Wing 1        | `wing1.png`                  | The sprite for the first wing.            |
| Wing 2        | `wing2.png`                  | The sprite for the second wing.           |

## File Structure

All listed files are located within the `data/ragdolls/sheep_fly/` directory.

## Usage in Modding

When creating or modifying ragdolls, you would reference these filenames within the corresponding entity or ragdoll configuration files to define the visual appearance and structure of the ragdoll. For example, in an entity's XML definition, you might see entries like:

```xml
<Ragdoll>
    <Part name="head" filename="data/ragdolls/sheep_fly/head.png" />
    <Part name="right_torso" filename="data/ragdolls/sheep_fly/right_torso.png" />
    <!-- ... other parts ... -->
</Ragdoll>