---
title: Sheep Ingestion Logic
category: scripts
---

# Sheep Ingestion Logic

This script defines the behavior of sheep when they ingest materials in Noita. It primarily focuses on what happens when a sheep consumes a specific material and in what quantity.

## Core Functions

### `inhaled_material( material, count )`

This function is called when a sheep "inhales" a material. The `material` parameter specifies the type of material inhaled, and `count` indicates the quantity. Currently, this function is empty and serves as a placeholder for potential future functionality.

### `ingested_material( material, count )`

This function is called when a sheep "ingests" a material.

*   **`material`**: A string representing the name of the ingested material (e.g., "dirt", "water").
*   **`count`**: An integer representing the quantity of the material ingested.

This function currently only prints the ingested material and its count to the game's console for debugging purposes.

```lua
function ingested_material( material, count )
	print( material, count )
end
```

## Key Attributes/Elements

*   **Material Identification**: The script relies on identifying the `material` string to determine what the sheep has consumed.
*   **Quantity Tracking**: The `count` parameter allows for tracking the amount of material ingested.
*   **Extensibility**: The presence of both `inhaled_material` and `ingested_material` functions suggests a design that can be expanded to handle different types of material consumption and trigger various in-game effects.