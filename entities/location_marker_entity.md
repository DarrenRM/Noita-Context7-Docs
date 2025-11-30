---
title: Location Marker Entity
category: entities
---

---

# Location Marker Entity

This entity represents a simple marker within the game world, primarily used for internal game logic and potentially for defining specific locations or points of interest.

## Entity Structure

The core of this entity is the `<Entity>` tag, which encapsulates its components.

## Key Components

### LocationMarkerComponent

This is the primary component for this entity.

*   **`id`**: A unique identifier for this location marker. In this case, it's set to `"0"`.

```xml
<Entity>
   <LocationMarkerComponent
       id="0" >
   </LocationMarkerComponent>
</Entity>