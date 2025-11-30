---
title: Seamine Death Script
category: scripts
---

---

# Seamine Death Script

This script defines the behavior when a "Seamine" entity is destroyed.

## Function: `death`

This function is called when the Seamine entity takes fatal damage.

### Parameters

| Parameter             | Type   | Description                                                              |
| --------------------- | ------ | ------------------------------------------------------------------------ |
| `damage_type_bit_field` | number | A bitfield representing the type of damage taken.                        |
| `damage_message`      | string | A descriptive message about the damage taken.                            |
| `entity_thats_responsible` | entity | The entity that caused the damage (if applicable).                       |
| `drop_items`          | bool   | Whether items should be dropped upon death.                              |

### Behavior

- **Logs Destruction:** Prints a message to the console indicating the Seamine's destruction and its coordinates.
- **Entity ID Retrieval:** Retrieves the unique ID of the destroyed entity.
- **Position Retrieval:** Gets the X and Y coordinates of the destroyed entity.
- **Potential Effects (Commented Out):** The script includes commented-out code that suggests the possibility of adding visual effects or particle emissions upon destruction. This is a placeholder for future modding enhancements.