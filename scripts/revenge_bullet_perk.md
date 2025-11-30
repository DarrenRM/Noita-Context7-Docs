---
title: Revenge Bullet Perk
category: scripts
---

---

# Revenge Bullet Perk

This perk allows the player to retaliate when taking damage by firing a projectile back at the attacker.

## Core Functionality

The `damage_received` function is the heart of this perk. It triggers when the player entity takes damage.

### Key Attributes & Logic

*   **Damage Threshold:** The perk only triggers for positive damage values (i.e., not healing).
*   **Self-Damage Prevention:** It prevents retaliation if the damage was caused by the player's own projectiles or their parent entity.
*   **Fire Rate Limiter:** Uses `script_wait_frames( entity_id, 2 )` to ensure projectiles are not fired too rapidly (every 2 frames).
*   **Projectile Source:** If the incoming projectile has a `VariableStorageComponent` with a `projectile_file` variable, that projectile will be used for the revenge shot.
*   **Targeting:**
    *   If the attacker entity is known, the revenge projectile will be aimed directly at the attacker's position.
    *   A small random angle offset (`angle_random`) is applied for variation.
*   **Damage Amplification:** The revenge projectile's damage is doubled compared to the original projectile's damage.

### Important Variables

| Variable        | Description