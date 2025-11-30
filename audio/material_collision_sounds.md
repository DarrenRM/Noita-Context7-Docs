---
title: Material Collision Sounds
category: audio
---

# Material Collision Sounds

This documentation describes the `material_relations.csv` file, which defines how different materials interact audibly when colliding. It maps material types to specific sound effects triggered by collisions.

## Overview

The `material_relations.csv` file is a comma-separated value (CSV) file that establishes relationships between various in-game materials and their corresponding collision sound effects. Each row represents a material, and the columns indicate which sound effect is played when that material collides with another.

## Key Attributes

The primary function of this file is to define the sound played when a material collides with *any* other material. The structure is as follows:

*   **Material Name:** The first column identifies the material being configured.
*   **Collision Sound:** Subsequent columns, up to a certain point, specify the sound effect played when this material collides with the material listed in the corresponding column header. If a cell is empty, it means no specific sound is defined for that particular material-to-material collision.

### Important Note on Sound Definitions

The file primarily uses a simplified approach: if a material has a sound defined in a specific column, that sound is generally used for collisions with the material indicated by that column's header. However, the most common and important sound is often the one listed in the *last* few columns, which acts as a general collision sound for that material.

## Key Materials and Their Collision Sounds

The following table highlights some of the key materials and their associated collision sounds. The presence of a sound effect in a column indicates that it will be played when the material in the row collides with the material in the column header.

| Material Name    | rock          | wood          | woodwall      | metalhollow   | metalhollow_barrel | metalhollow_gold | metalwall     | metalchain    | electricwire  | meat          | organicsoft   | organicbouncy | ceramic       | ice           | glass         | glass_potion  | gold          | bone          | sand          | gravel        | snow          | cloth         | liquid        | slime         | character_player | projectile    |
| :--------------- | :------------ | :------------ | :------------ | :------------ | :----------------- | :--------------- | :------------ | :------------ | :------------ | :------------ | :------------ | :------------ | :------------ | :------------ | :------------ | :------------ | :------------ | :------------ | :------------ | :------------ | :------------ | :------------ | :------------ | :------------ | :--------------- | :------------ |
| **rock**         | collision/rock |               |               |               |                    |                  |               |               |               |               |               |               |               |               |               |               |               |               |               |               |               |               |               |               | rock             | rock          |
| **wood**         |               | collision/wood |               |               |                    |                  |               |               |               |               |               |               |               |               |               |               |               |               |               |               |               |               |               |               | wood             | rock          |
| **woodwall**     |               |               | collision/woodwall |               |                    |                  |               |               |               |               |               |               |               |               |               |               |               |               |               |               |               |               |               |               | wood             | wood          |
| **metalhollow**  |               |               |               | collision/metalhollow |                    |                  |               |               |               |               |               |               |               |               |               |               |               |               |               |               |               |               |               |               | metal            | metal         |
| **metalhollow_barrel** |               |               |               |               | collision/metalhollow_barrel |                  |               |               |               |               |               |               |               |               |               |               |               |               |               |               |               |               |               |               | metal            | metal         |
| **metalwall**    |               |               |               |               |                    |                  | collision/metalwall |               |               |               |               |               |               |               |               |               |               |               |               |               |               |               |               |               | metal            | metal         |
| **electricwire** |               |               |               |               |                    |                  |               |               | collision/electricwire |               |               |               |               |               |               |               |               |               |               |               |               |               |               |               |                  |               |
| **meat**         |               |               |               |               |                    |                  |               |               |               | collision/meat |               |               |               |               |               |               |               |               |               |               |               |               |               | slime         | organic          | organic       |
| **organicsoft**  |               |               |               |               |                    |                  |               |               |               |               | collision/meat |               |               |               |               |               |               |               |               |               |               |               |               |               | gravel           | organic       |
| **organicbouncy**|               |               |               |               |                    |                  |               |               |               |               |               | collision/meatbouncy |               |               |               |               |               |               |               |               |               |               |               |               | gravel           | organic       |
| **ceramic**      | collision/rock |               |               |               |                    |                  |               |               |               |               |               |               |               |               |               |               |               |               |               |               |               |               |               |               | rock             | rock          |
| **ice**          |               |               |               |               |                    |                  |               |               |               |               |               |               |               | collision/ice |               |               |               |               |               |               |               |               |               |               | ice              | rock          |
| **glass**        |               |               |               |               |                    |                  |               |               |               |               |               |               |               |               | collision/glass |               |               |               |               |               |               |               |               |               | ice              | rock          |
| **glass_potion** |               |               |               |               |                    |                  |               |               |               |               |               |               |               |               |               | collision/glasspotion |               |               |               |               |               |               |               |               | ice              | rock          |
| **gold**         |               |               |               |               |                    |                  |               |               |               |               |               |               |               |               |               |               | collision/gold |               |               |               |               |               |               |               | rock             | rock          |
| **bone**         |               |               |               |               |                    |                  |               |               |               |               |               |               |               |               |               |               |               | collision/bone |               |               |               |               |               |               | rock             | rock          |
| **sand**         |               |               |               |               |                    |                  |               |               |               |               |               |               |               |               |               |               |               |               | collision/sand |               |               |               |               |               | sand             | rock          |
| **gravel**       |               |               |               |               |                    |                  |               |               |               |               |               |               |               |               |               |               |               |               |               | collision/gravel |               |               |               |               | gravel           | rock          |
| **snow**         |               |               |               |               |                    |                  |               |               |               |               |               |               |               |               |               |               |               |               |               |               | collision/snow |               |               |               | snow             | organic       |
| **liquid**       |               |               |               |               |                    |                  |               |               |               |               |               |               |               |               |               |               |               |               |               |               |               |               | water         | water         | water            | water         |
| **slime**        |               |               |               |               |                    |                  |               |               |               |               |               |               |               |               |               |               |               |               |               |               |               |               |               |               | slime            | rock          |

## Summary of Common Collision Sounds

Many materials share common collision sound categories, simplifying the overall sound design. These include:

*   **rock:** A general hard, percussive sound.
*   **wood:** A duller, more resonant impact sound.
*   **metal:** A sharp, metallic clang.
*   **organic:** Sounds associated with biological matter.
*   **ice:** A brittle, cracking sound.
*   **water:** A splashing or gurgling sound.
*   **slime:** A viscous, squelching sound.

## AI Modding Considerations

When creating or modifying sounds for materials, consider the following:

1.  **Material Type:** Understand the physical properties of the material you are modifying (e.g., is it hard, soft, brittle, metallic?).
2.  **Collision Partner:** While the file often uses a general sound, the specific material it collides with can influence the perceived impact.
3.  **Sound Asset Path:** Ensure that the sound effect files referenced in the CSV exist in the correct `data/audio/` subfolders.
4.  **Consistency:** Aim for consistent sound profiles for similar material types to maintain a cohesive audio experience.
5.  **Experimentation:** The CSV format allows for fine-tuning specific material-to-material interactions. Don't hesitate to experiment with unique sounds for rare or important collision pairs.

This file is crucial for defining the tactile feedback of the game world through sound. Modifying it can significantly alter the player's perception of material interactions.