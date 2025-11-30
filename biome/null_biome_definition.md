---
title: Null Biome Definition
category: biome
---

# Null Biome Definition

This document describes the `null.xml` file, which defines a placeholder or "null" biome in Noita. This biome is typically used as a default or fallback when a specific biome cannot be determined.

## Biome Definition

The core of the biome definition is the `<Biome>` tag.

### Key Attributes

*   **`name`**: The internal name of the biome. In this case, it's "unknown", indicating its placeholder nature.

```xml
<Biome name="unknown">
  <!-- Biome content -->
</Biome>
```

## Topology

The `<Topology>` tag defines the physical structure and generation of the biome.

### Key Attributes

*   **`name`**: The name of the topology. Here, it's "NULL", reinforcing the placeholder concept.

```xml
<Topology name="NULL">
  <!-- Topology specific settings -->
</Topology>
```

## Materials

The `<Materials>` tag specifies the primary materials that make up the biome.

### Key Attributes

*   **`name`**: The name of the material set. Here, it's "forest", suggesting a default material set might be applied if this biome were ever to be rendered with actual content.

```xml
<Materials name="forest">
  <!-- Material specific settings -->
</Materials>
```