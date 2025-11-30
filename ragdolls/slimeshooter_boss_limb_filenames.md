---
title: Slimeshooter Boss Limb Filenames
category: data/ragdolls
---

# Slimeshooter Boss Limb Filenames

This document outlines the image filenames used for the ragdoll components of the Slimeshooter boss in Noita. These files are essential for defining the visual appearance and animation of the boss's various body parts.

## Key Components

The following are the primary image files used for the Slimeshooter boss's ragdoll:

### Torso
*   `torso_boss_limbs.png`: The main body segment of the Slimeshooter boss.

### Tentacles
The Slimeshooter boss features multiple tentacles, each with two variations (likely for animation or different states).

*   `tentacle_1_a.png`
*   `tentacle_1_b.png`
*   `tentacle_2_a.png`
*   `tentacle_2_b.png`
*   `tentacle_3_a.png`
*   `tentacle_3_b.png`
*   `tentacle_4_a.png`
*   `tentacle_4_b.png`

## Usage in Modding

When creating or modifying the Slimeshooter boss, these filenames are referenced within the entity's configuration files (e.g., `.xml` files) to link the visual assets to the ragdoll system. Modders can replace these images with custom assets to alter the boss's appearance.

**Example (Conceptual - actual implementation may vary):**

```xml
<Entity name="slimeshooter_boss">
    <RagdollComponent
        image_file="data/ragdolls/slimeshooter/torso_boss_limbs.png"
        -- ... other ragdoll properties
    >
        <Limb name="tentacle_1" image_file="data/ragdolls/slimeshooter/tentacle_1_a.png" />
        <Limb name="tentacle_2" image_file="data/ragdolls/slimeshooter/tentacle_2_a.png" />
        <!-- ... more limbs -->
    </RagdollComponent>
    <!-- ... other components -->
</Entity>
```

**Note:** The exact structure and attributes within the entity configuration files may differ. Refer to existing Noita entity files for precise implementation details.