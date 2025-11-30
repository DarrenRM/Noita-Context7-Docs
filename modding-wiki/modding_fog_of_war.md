---
title: Modding: Fog of War
source: https://noita.wiki.gg/wiki/Modding:_Fog_of_War
category: modding-wiki
---

# Modding: Fog of War

This documentation covers how to interact with and modify Noita's fog of war system through modding. Understanding these mechanics is crucial for creating entities or effects that reveal or interact with the game's hidden areas.

## Player Fog of War Clearing

To make an entity permanently clear the fog of war, similar to the default player character, it requires a specific set of components.

The following components are necessary for an entity to create permanent holes in the fog of war:

*   [CharacterDataComponent](https://noita.wiki.gg/wiki/Documentation:_CharacterDataComponent)
*   [CharacterPlatformingComponent](https://noita.wiki.gg/wiki/Documentation:_CharacterPlatformingComponent)
*   [ControlsComponent](https://noita.wiki.gg/wiki/Documentation:_ControlsComponent)
*   [Inventory2Component](https://noita.wiki.gg/wiki/Documentation:_Inventory2Component)
*   [PlatformShooterPlayerComponent](https://noita.wiki.gg/wiki/Documentation:_PlatformShooterPlayerComponent)

While it's technically possible to have multiple entities with these components, it's generally not recommended as the game may not be designed to handle multiple entities simultaneously clearing the fog of war, potentially leading to issues.

## Components That Interact with Fog of War

Several components can be used to influence or interact with the fog of war.

*   **[Documentation: FogOfWarRadiusComponent](https://noita.wiki.gg/wiki/Documentation:_FogOfWarRadiusComponent)**: This component likely controls the radius around an entity that affects fog of war visibility.
*   **[Documentation: FogOfWarRemoverComponent](https://noita.wiki.gg/wiki/Documentation:_FogOfWarRemoverComponent)**: This component is designed to remove fog of war within its defined area.
*   **[Documentation: MagicXRayComponent](https://noita.wiki.gg/wiki/Documentation:_MagicXRayComponent)**: This component creates permanent holes in the Fog of War.
*   **[Documentation: SpriteComponent](https://noita.wiki.gg/wiki/Documentation:_SpriteComponent)**: The `fog_of_war_hole` member within this component can be used to create fog of war holes associated with a sprite.
*   **[Documentation: WorldStateComponent](https://noita.wiki.gg/wiki/Documentation:_WorldStateComponent)**: The `open_fog_of_war_everywhere` member of this component can be used to reveal the entire fog of war.
*   **[Documentation: MusicEnergyAffectorComponent](https://noita.wiki.gg/wiki/Documentation:_MusicEnergyAffectorComponent)**: The `fog_of_war_threshold` member of this component might relate to fog of war visibility based on music energy levels.
*   **[Documentation: AudioComponent](https://noita.wiki.gg/wiki/Documentation:_AudioComponent)**: The `play_only_if_visible` member of this component can restrict audio playback to only occur when the entity is visible within the fog of war.