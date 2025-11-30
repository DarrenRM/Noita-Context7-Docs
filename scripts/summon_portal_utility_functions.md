---
title: Summon Portal Utility Functions
category: scripts/
---

# Summon Portal Utility Functions

This script provides utility functions for determining the spawn position of portals within specific biome boundaries.

## Key Functions

### `get_portal_position()`

This function calculates and returns a random X and Y coordinate for a portal.

#### Parameters

None.

#### Returns

*   `portal_x` (number): The calculated X-coordinate for the portal.
*   `portal_y` (number): The calculated Y-coordinate for the portal.

#### Logic

The function defines biome boundaries and a rim offset to ensure portals spawn within a designated area. It then uses `ProceduralRandomi` to generate random coordinates within these constraints.

#### Biome Boundaries

*   `biome_x_min`: -2450
*   `biome_x_max`: 1900
*   `biome_y_min`: 6700
*   `biome_y_max`: 8000
*   `rim`: 200 (Offset from biome edges)