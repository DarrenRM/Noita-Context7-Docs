---
title: Wand Level 10 Procedural Generation
category: scripts
---

# Wand Level 10 Procedural Generation

This script defines the parameters for generating a Level 10 wand procedurally in Noita. It utilizes the `gun_procedural.lua` library to create wands with specific characteristics.

## Core Generation Function

The primary function called is `generate_gun`.

```lua
dofile_once("data/scripts/gun/procedural/gun_procedural.lua")

generate_gun( 200, 11, false )
```

*   **`200`**: This likely represents a base value or identifier related to the wand's power or complexity.
*   **`11`**: This is the specific wand level being generated (Level 10).
*   **`false`**: This boolean likely controls whether the wand is a "special" or unique variant. `false` indicates a standard procedural generation.

## Key Attributes (Implied by `generate_gun` parameters)

While the script itself is minimal, the `generate_gun` function in `gun_procedural.lua` would be responsible for determining the following key attributes for a Level 10 wand:

### 1. Spell Slots
*   **Number of Spell Slots**: Level 10 wands typically have a significant number of spell slots, allowing for complex spell combinations.

### 2. Recharge Time
*   **Recharge Time**: Expected to be relatively low, enabling rapid firing.

### 3. Mana Capacity
*   **Mana Capacity**: High mana capacity is characteristic of higher-level wands.

### 4. Spell Costs
*   **Spell Costs**: The cost of casting spells from this wand will be influenced by its level and the spells attached.

### 5. Projectile Speed
*   **Projectile Speed**: Wands at this level can often fire projectiles at higher speeds.

### 6. Spread
*   **Spread**: The degree of spread for projectiles can be controlled, allowing for focused or dispersed attacks.

### 7. Randomization Factors
*   **Randomization**: The `generate_gun` function will incorporate various randomization elements to ensure each Level 10 wand generated is unique. This includes the selection and arrangement of spells.

### 8. Potential for Powerful Spells
*   **Spell Pool**: The pool of spells available for selection will be weighted towards more powerful and advanced spells suitable for a Level 10 wand.

### 9. Rarity
*   **Rarity**: Level 10 wands are generally rarer finds in the game.

### 10. Damage Output
*   **Damage**: The combined damage output of spells cast from this wand will be substantial due to its level and potential spell combinations.