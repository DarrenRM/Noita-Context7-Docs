---
title: Thundermage Ragdoll Sprites
category: ragdolls
---

---

# Thundermage Ragdoll Sprites

This documentation outlines the sprite assets used for the "Thundermage" ragdoll in Noita. These files define the visual components of the character's body when it is in a ragdoll state.

## Sprite Components

The following image files define the individual parts of the Thundermage ragdoll. These are typically used in conjunction with a ragdoll definition file (e.g., `.xml`) to assemble the complete ragdoll.

### Key Sprite Parts

*   **torso.png**: The main body segment.
*   **head.png**: The character's head.
*   **hood.png**: An accessory, likely a hood, for the head.
*   **right_arm.png**: The right arm segment.
*   **right_hand.png**: The right hand segment.
*   **right_thigh.png**: The right thigh segment.
*   **right_foot.png**: The right foot segment.
*   **left_arm.png**: The left arm segment.
*   **left_hand.png**: The left hand segment.
*   **left_thigh.png**: The left thigh segment.
*   **left_foot.png**: The left foot segment.

## File Structure

The sprite assets for the Thundermage ragdoll are located within the `data/ragdolls/thundermage/` directory.

```
data/ragdolls/thundermage/
├── torso.png
├── right_thigh.png
├── right_foot.png
├── right_arm.png
├── right_hand.png
├── left_thigh.png
├── left_foot.png
├── left_arm.png
├── left_hand.png
├── head.png
└── hood.png
```

## Usage in Modding

These sprite files are essential for creating or modifying ragdoll entities. Modders will typically reference these `.png` files within an XML definition for a ragdoll, specifying their position, rotation, and connection points to other body parts.

**Example Snippet (Conceptual - actual XML will vary):**

```xml
<ragdoll>
    <part name="torso" sprite="data/ragdolls/thundermage/torso.png" />
    <part name="head" sprite="data/ragdolls/thundermage/head.png" parent="torso" />
    <!-- ... other parts ... -->
</ragdoll>
```