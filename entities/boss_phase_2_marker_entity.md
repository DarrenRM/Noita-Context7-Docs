---
title: Boss Phase 2 Marker Entity
category: entities
---

# Boss Phase 2 Marker Entity

This entity serves as a marker to keep the boss alive across serialization events, particularly during phase transitions.

## Key Components

### Entity
- **Tags**: `boss_phase2_marker` - Identifies this entity as a marker for the boss's second phase.

### VariableStorageComponent
- This component is present to ensure the entity persists through game serialization. It doesn't have any specific configurable attributes listed in this snippet, but its presence is crucial for maintaining the boss's state.