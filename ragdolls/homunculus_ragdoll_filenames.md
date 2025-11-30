---
title: Homunculus Ragdoll Filenames
category: ragdolls
---

---

# Homunculus Ragdoll Filenames

This documentation outlines the image filenames used for the Homunculus ragdoll in Noita. These files define the visual components of the Homunculus's physical form.

## Key Components

The Homunculus ragdoll is composed of several distinct image files, each representing a part of its body.

### Torso
- **Filename:** `data/ragdolls/homunculus/torso.png`
- **Description:** The central body mass of the Homunculus.

### Head
- **Filename:** `data/ragdolls/homunculus/head.png`
- **Description:** The head of the Homunculus.

### Left Arm
- **Filename:** `data/ragdolls/homunculus/arm_l.png`
- **Description:** The left arm of the Homunculus.

### Right Arm
- **Filename:** `data/ragdolls/homunculus/arm_r.png`
- **Description:** The right arm of the Homunculus.

### Left Foot
- **Filename:** `data/ragdolls/homunculus/foot_l.png`
- **Description:** The left foot of the Homunculus.

### Right Foot
- **Filename:** `data/ragdolls/homunculus/foot_r.png`
- **Description:** The right foot of the Homunculus.

## Usage in Modding

When creating or modifying ragdolls for custom entities, understanding these filename conventions is crucial. You would typically reference these image paths within the entity's XML definition to specify which visual assets make up its ragdoll. For example, in an entity's XML, you might find a section like:

```xml
<Ragdoll>
    <Torso filename="data/ragdolls/homunculus/torso.png" />
    <Head filename="data/ragdolls/homunculus/head.png" />
    <LeftArm filename="data/ragdolls/homunculus/arm_l.png" />
    <RightArm filename="data/ragdolls/homunculus/arm_r.png" />
    <LeftFoot filename="data/ragdolls/homunculus/foot_l.png" />
    <RightFoot filename="data/ragdolls/homunculus/foot_r.png" />
    <!-- Other ragdoll properties -->
</Ragdoll>
```

This structure allows the game engine to load and assemble the visual components of the ragdoll correctly.