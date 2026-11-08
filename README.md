# Unity Essentials

Packages for Unity 6 and HDRP, each in its own git repository, for runtime systems, editor
tools, rendering, the environment, humanoid characters and UI Toolkit. This package,
`com.unityessentials.core`, adds an editor window that lists the packages of the
[EggyStudio](https://github.com/EggyStudio) account and installs the ones selected, together with
the packages they depend on.

> All scripts are contained within the `UnityEssentials` namespace.

## Installation

1. **Add the package** via Unity's Package Manager
    - Window → Package Manager → "+" → "Add package from git URL…"
    - Paste the following:
    ```
    https://github.com/EggyStudio/UnityEssentials.git
    ```

2. **Install modules** from the Tools menu
    - Tools → UnityEssentials → Install & Update
    - Select individual modules or install all; run again anytime to update

Dependencies between modules are resolved automatically.

Tools → UnityEssentials → Initialize Addressables creates the project's Addressables settings,
which several packages load their assets from. The package does the same after each script reload.

## Packages

A package marked not implemented holds only its manifest and assembly definition, and installs
without adding any code.

### Core & HDRP
HDRP setup shared by the other packages.
- [Unity.Core.HDRP.ImGui](https://github.com/EggyStudio/Unity.Core.HDRP.ImGui), Dear ImGui rendered through an HDRP Custom Pass in Edit Mode and Play Mode
- [Unity.Core.HDRP.Resources](https://github.com/EggyStudio/Unity.Core.HDRP.Resources), default HDRP Asset, Global Settings, LookDev and Volume profiles
- [Unity.Core.HDRP.Settings](https://github.com/EggyStudio/Unity.Core.HDRP.Settings), HDRP runtime options as a component, saved to JSON
- [Unity.Core.Templates.Sponza](https://github.com/EggyStudio/Unity.Core.Templates.Sponza), spawns a Sponza scene setup from the GameObject menu

### Dependencies
Integrations with outside tools that other packages and the editor window use.
- [Unity.Dependencies.Addressables](https://github.com/EggyStudio/Unity.Dependencies.Addressables)
- [Unity.Dependencies.GitApi](https://github.com/EggyStudio/Unity.Dependencies.GitApi), fetch, pull, stage, commit and push for a selected folder
- [Unity.Dependencies.GitHub](https://github.com/EggyStudio/Unity.Dependencies.GitHub), clones several GitHub repositories into the project
- [Unity.Dependencies.NuGet](https://github.com/EggyStudio/Unity.Dependencies.NuGet), NuGet package management in the editor through NuGetForUnity

### Diagnostics
In-game debugging tools drawn with ImGui.
- [Unity.Diagnostics.Console](https://github.com/EggyStudio/Unity.Diagnostics.Console)
- [Unity.Diagnostics.Gizmo](https://github.com/EggyStudio/Unity.Diagnostics.Gizmo), in-game move, rotate and scale gizmo
- [Unity.Diagnostics.Modules](https://github.com/EggyStudio/Unity.Diagnostics.Modules), frame time overlay with FPS, render time, memory and GC spikes
- [Unity.Diagnostics.Monitoring](https://github.com/EggyStudio/Unity.Diagnostics.Monitoring), live values of annotated fields, properties, events and methods
- [Unity.Diagnostics.ToggleShortcut](https://github.com/EggyStudio/Unity.Diagnostics.ToggleShortcut)

### Editor Attributes
Attributes that change how a serialized field or a method appears in the Inspector.
- [Unity.Editor.Attributes.Button](https://github.com/EggyStudio/Unity.Editor.Attributes.Button), methods as Inspector buttons
- [Unity.Editor.Attributes.DateTime](https://github.com/EggyStudio/Unity.Editor.Attributes.DateTime), date and time pickers
- [Unity.Editor.Attributes.Directory](https://github.com/EggyStudio/Unity.Editor.Attributes.Directory), folder picker for string fields
- [Unity.Editor.Attributes.Foldout](https://github.com/EggyStudio/Unity.Editor.Attributes.Foldout), fields grouped under nested foldouts
- [Unity.Editor.Attributes.Info](https://github.com/EggyStudio/Unity.Editor.Attributes.Info), info, warning and error help boxes
- [Unity.Editor.Attributes.LabelOverride](https://github.com/EggyStudio/Unity.Editor.Attributes.LabelOverride), a field's label replaced by another
- [Unity.Editor.Attributes.MinMaxSlider](https://github.com/EggyStudio/Unity.Editor.Attributes.MinMaxSlider), one slider for a minimum and maximum pair
- [Unity.Editor.Attributes.OnValueChanged](https://github.com/EggyStudio/Unity.Editor.Attributes.OnValueChanged), a method called when a field changes
- [Unity.Editor.Attributes.ReadOnly](https://github.com/EggyStudio/Unity.Editor.Attributes.ReadOnly), fields shown without editing
- [Unity.Editor.Attributes.ShowIf](https://github.com/EggyStudio/Unity.Editor.Attributes.ShowIf), fields shown or disabled by another field's value
- [Unity.Editor.Attributes.ToggleButton](https://github.com/EggyStudio/Unity.Editor.Attributes.ToggleButton), booleans as toggle buttons

### Editor Components & Drawers
Property drawers, editor windows and components for the editor.
- [Unity.Editor.Components.StickyNote](https://github.com/EggyStudio/Unity.Editor.Components.StickyNote), color-coded notes on GameObjects
- [Unity.Editor.Drawer.Console](https://github.com/EggyStudio/Unity.Editor.Drawer.Console)
- [Unity.Editor.Drawer.DomainReload](https://github.com/EggyStudio/Unity.Editor.Drawer.DomainReload)
- [Unity.Editor.Drawer.Enum](https://github.com/EggyStudio/Unity.Editor.Drawer.Enum), enum popup with search and keyboard navigation
- [Unity.Editor.Drawer.EnumFlags](https://github.com/EggyStudio/Unity.Editor.Drawer.EnumFlags), checkboxes for flag enums
- [Unity.Editor.Drawer.MarkdownViewer](https://github.com/EggyStudio/Unity.Editor.Drawer.MarkdownViewer)
- [Unity.Editor.Drawer.PackageManifest](https://github.com/EggyStudio/Unity.Editor.Drawer.PackageManifest), editor window for `package.json` files
- [Unity.Editor.Drawer.ReorderableList](https://github.com/EggyStudio/Unity.Editor.Drawer.ReorderableList)
- [Unity.Editor.Drawer.SceneReference](https://github.com/EggyStudio/Unity.Editor.Drawer.SceneReference), serializable scene reference with loading by code
- [Unity.Editor.Drawer.ScriptableObject](https://github.com/EggyStudio/Unity.Editor.Drawer.ScriptableObject), ScriptableObject references edited inline
- [Unity.Editor.Drawer.SerializedDictionary](https://github.com/EggyStudio/Unity.Editor.Drawer.SerializedDictionary), serializable dictionary with a reorderable list
- [Unity.Editor.Drawer.SimpleTreeView](https://github.com/EggyStudio/Unity.Editor.Drawer.SimpleTreeView), IMGUI TreeView with drag and drop, renaming and context menus
- [Unity.Editor.Drawer.WindowBuilder](https://github.com/EggyStudio/Unity.Editor.Drawer.WindowBuilder), fluent API for EditorWindow layouts

### Editor Hooks, Fetchers & Tools
Callbacks into the editor's own windows and loops, and standalone editor tools.
- [Unity.Editor.Fetcher.MouseInput](https://github.com/EggyStudio/Unity.Editor.Fetcher.MouseInput), OS cursor position on Windows, macOS and Linux
- [Unity.Editor.Hooks.Hierarchy](https://github.com/EggyStudio/Unity.Editor.Hooks.Hierarchy), Hierarchy selection events and helpers
- [Unity.Editor.Hooks.Inspector](https://github.com/EggyStudio/Unity.Editor.Hooks.Inspector), prioritized hooks into MonoBehaviour inspectors
- [Unity.Editor.Hooks.PlayerLoop](https://github.com/EggyStudio/Unity.Editor.Hooks.PlayerLoop), delegates added to and removed from PlayerLoop phases
- [Unity.Editor.Hooks.Statusbar](https://github.com/EggyStudio/Unity.Editor.Hooks.Statusbar)
- [Unity.Editor.Hooks.TextAsset](https://github.com/EggyStudio/Unity.Editor.Hooks.TextAsset)
- [Unity.Editor.Hooks.Toolbar](https://github.com/EggyStudio/Unity.Editor.Hooks.Toolbar)
- [Unity.Editor.Hooks.UIBuilder](https://github.com/EggyStudio/Unity.Editor.Hooks.UIBuilder), access to the UI Builder window and its selection
- [Unity.Editor.Tools.EditorIcons](https://github.com/EggyStudio/Unity.Editor.Tools.EditorIcons), search and export of Unity's built-in editor icons
- [Unity.Editor.Tools.MaskMapGenerator](https://github.com/EggyStudio/Unity.Editor.Tools.MaskMapGenerator), metallic, AO, detail mask and smoothness packed into one texture

### Environment
Time of day, sun and moon, weather and water for HDRP scenes.
- [Unity.Environment.Atmosphere](https://github.com/EggyStudio/Unity.Environment.Atmosphere), not implemented
- [Unity.Environment.CelestialBodies](https://github.com/EggyStudio/Unity.Environment.CelestialBodies), sun and moon positions and the lights they drive
- [Unity.Environment.Clouds](https://github.com/EggyStudio/Unity.Environment.Clouds), not implemented
- [Unity.Environment.Ecosystem](https://github.com/EggyStudio/Unity.Environment.Ecosystem), not implemented
- [Unity.Environment.Fauna](https://github.com/EggyStudio/Unity.Environment.Fauna), not implemented
- [Unity.Environment.Flora](https://github.com/EggyStudio/Unity.Environment.Flora), not implemented
- [Unity.Environment.Ocean](https://github.com/EggyStudio/Unity.Environment.Ocean), ocean and pool water prefabs
- [Unity.Environment.Precipitation](https://github.com/EggyStudio/Unity.Environment.Precipitation), not implemented
- [Unity.Environment.Terrain](https://github.com/EggyStudio/Unity.Environment.Terrain), not implemented
- [Unity.Environment.TimeOfDay](https://github.com/EggyStudio/Unity.Environment.TimeOfDay), sun and moon set from date, time and location
- [Unity.Environment.Vegetation](https://github.com/EggyStudio/Unity.Environment.Vegetation), not implemented
- [Unity.Environment.Weather](https://github.com/EggyStudio/Unity.Environment.Weather), weather prefab with cloud layer, volumetric cloud and fog volumes
- [Unity.Environment.Wind](https://github.com/EggyStudio/Unity.Environment.Wind), not implemented

### Graphics & Rendering
HDRP lights, probes, lighting scenarios and color grading.
- [Unity.Graphics.AdvancedAtmosphere](https://github.com/EggyStudio/Unity.Graphics.AdvancedAtmosphere), not implemented
- [Unity.Graphics.AdvancedSky](https://github.com/EggyStudio/Unity.Graphics.AdvancedSky), not implemented
- [Unity.Graphics.AdvancedSpotLight](https://github.com/EggyStudio/Unity.Graphics.AdvancedSpotLight), spot light split into RGB lights for chromatic aberration
- [Unity.Graphics.AdvancedTerrain](https://github.com/EggyStudio/Unity.Graphics.AdvancedTerrain), not implemented
- [Unity.Graphics.AdvancedVolumetrics](https://github.com/EggyStudio/Unity.Graphics.AdvancedVolumetrics), not implemented
- [Unity.Graphics.AdvancedWater](https://github.com/EggyStudio/Unity.Graphics.AdvancedWater), not implemented, and without a `package.json` it does not install
- [Unity.Graphics.ApvLightingBaker](https://github.com/EggyStudio/Unity.Graphics.ApvLightingBaker), Adaptive Probe Volume lighting scenarios baked by name
- [Unity.Graphics.BlackoutReflectionProbe](https://github.com/EggyStudio/Unity.Graphics.BlackoutReflectionProbe), reflection probe that returns black inside its bounds
- [Unity.Graphics.LightCookies](https://github.com/EggyStudio/Unity.Graphics.LightCookies), IES light profiles for HDRP lights
- [Unity.Graphics.Tonemaps](https://github.com/EggyStudio/Unity.Graphics.Tonemaps), AgX-inspired tonemapping LUTs

### Humanoid
Ragdolls, poses and look targets for humanoid characters.
- [Unity.Humanoid.ActiveRagdoll](https://github.com/EggyStudio/Unity.Humanoid.ActiveRagdoll), physics ragdoll that follows the animation with a PD controller
- [Unity.Humanoid.AdvancedAvatar](https://github.com/EggyStudio/Unity.Humanoid.AdvancedAvatar), not implemented
- [Unity.Humanoid.AnimationRigging](https://github.com/EggyStudio/Unity.Humanoid.AnimationRigging), head and aim look target with clamping and smoothing
- [Unity.Humanoid.PoseController](https://github.com/EggyStudio/Unity.Humanoid.PoseController), humanoid poses set through muscle values
- [Unity.Humanoid.RagdollBuilder](https://github.com/EggyStudio/Unity.Humanoid.RagdollBuilder), humanoid ragdoll generation with editable colliders and joints

### Movement
Character and camera controllers.
- [Unity.Movement.AdvancedCharacterController](https://github.com/EggyStudio/Unity.Movement.AdvancedCharacterController), not implemented
- [Unity.Movement.SpectatorController](https://github.com/EggyStudio/Unity.Movement.SpectatorController), free-fly spectator camera

### Multiplayer
Sessions, matchmaking and social features. None of these is implemented.
- [Unity.Multiplayer.Backend.InterestManagement](https://github.com/EggyStudio/Unity.Multiplayer.Backend.InterestManagement)
- [Unity.Multiplayer.Backend.WorldPartition](https://github.com/EggyStudio/Unity.Multiplayer.Backend.WorldPartition)
- [Unity.Multiplayer.Communication.Chat](https://github.com/EggyStudio/Unity.Multiplayer.Communication.Chat)
- [Unity.Multiplayer.Communication.Voice](https://github.com/EggyStudio/Unity.Multiplayer.Communication.Voice)
- [Unity.Multiplayer.Lobbies](https://github.com/EggyStudio/Unity.Multiplayer.Lobbies)
- [Unity.Multiplayer.Matchmaking](https://github.com/EggyStudio/Unity.Multiplayer.Matchmaking)
- [Unity.Multiplayer.P2P](https://github.com/EggyStudio/Unity.Multiplayer.P2P)
- [Unity.Multiplayer.P2P.Replication](https://github.com/EggyStudio/Unity.Multiplayer.P2P.Replication)
- [Unity.Multiplayer.P2P.Sessions](https://github.com/EggyStudio/Unity.Multiplayer.P2P.Sessions)
- [Unity.Multiplayer.Sessions](https://github.com/EggyStudio/Unity.Multiplayer.Sessions)
- [Unity.Multiplayer.Social.Friends](https://github.com/EggyStudio/Unity.Multiplayer.Social.Friends)
- [Unity.Multiplayer.Social.Groups](https://github.com/EggyStudio/Unity.Multiplayer.Social.Groups)
- [Unity.Multiplayer.Social.Invites](https://github.com/EggyStudio/Unity.Multiplayer.Social.Invites)

### Networking
Transport, relay and backend services. None of these is implemented.
- [Unity.Networking.Backend.Encryption](https://github.com/EggyStudio/Unity.Networking.Backend.Encryption)
- [Unity.Networking.Backend.NatTraversal](https://github.com/EggyStudio/Unity.Networking.Backend.NatTraversal)
- [Unity.Networking.Backend.PeerDiscovery](https://github.com/EggyStudio/Unity.Networking.Backend.PeerDiscovery)
- [Unity.Networking.Backend.Relay](https://github.com/EggyStudio/Unity.Networking.Backend.Relay)
- [Unity.Networking.Backend.Serialization](https://github.com/EggyStudio/Unity.Networking.Backend.Serialization)
- [Unity.Networking.Backend.Transport](https://github.com/EggyStudio/Unity.Networking.Backend.Transport)
- [Unity.Networking.Database](https://github.com/EggyStudio/Unity.Networking.Database)
- [Unity.Networking.Identity](https://github.com/EggyStudio/Unity.Networking.Identity)
- [Unity.Networking.Inventory](https://github.com/EggyStudio/Unity.Networking.Inventory)
- [Unity.Networking.Persistence](https://github.com/EggyStudio/Unity.Networking.Persistence)
- [Unity.Networking.Profiles](https://github.com/EggyStudio/Unity.Networking.Profiles)

### Rendering & Camera
Physical camera control, exposure and render rates.
- [Unity.Rendering.AdvancedCamera](https://github.com/EggyStudio/Unity.Rendering.AdvancedCamera)
- [Unity.Rendering.Camera.AutoExposure](https://github.com/EggyStudio/Unity.Rendering.Camera.AutoExposure), exposure adjusted from scene luminance
- [Unity.Rendering.Camera.FocusPoint](https://github.com/EggyStudio/Unity.Rendering.Camera.FocusPoint), focus distance from a ray or sphere cast
- [Unity.Rendering.Camera.Luminance](https://github.com/EggyStudio/Unity.Rendering.Camera.Luminance), average luminance of a camera's image, measured on the GPU
- [Unity.Rendering.Camera.PhysicalProperties](https://github.com/EggyStudio/Unity.Rendering.Camera.PhysicalProperties), presets for aperture, focal length, ISO and shutter
- [Unity.Rendering.Camera.RenderTexture](https://github.com/EggyStudio/Unity.Rendering.Camera.RenderTexture), camera output to a managed RenderTexture
- [Unity.Rendering.CameraRefreshRate](https://github.com/EggyStudio/Unity.Rendering.CameraRefreshRate), per-camera render rate limit
- [Unity.Rendering.GlobalRefreshRate](https://github.com/EggyStudio/Unity.Rendering.GlobalRefreshRate), frame limiter and global tick for time-sliced work

### Sound & Audio
An AudioMixer setup. Acoustics, playback, spatial audio, synthesis and voice are not implemented.
- [Unity.Sound.Acoustics](https://github.com/EggyStudio/Unity.Sound.Acoustics), not implemented
- [Unity.Sound.AudioMixer](https://github.com/EggyStudio/Unity.Sound.AudioMixer), AudioMixer with master, music, effects, voice and environment groups
- [Unity.Sound.Playback](https://github.com/EggyStudio/Unity.Sound.Playback), not implemented
- [Unity.Sound.SpatialAudio](https://github.com/EggyStudio/Unity.Sound.SpatialAudio), not implemented
- [Unity.Sound.Synthesis](https://github.com/EggyStudio/Unity.Sound.Synthesis), not implemented
- [Unity.Sound.Voice](https://github.com/EggyStudio/Unity.Sound.Voice), not implemented

### Systems
Runtime architecture, such as dependency injection, events, scene loading, settings and scheduling.
- [Unity.Systems.AssetResolver](https://github.com/EggyStudio/Unity.Systems.AssetResolver), typed asset lookup, Addressables first, with caching
- [Unity.Systems.CameraProvider](https://github.com/EggyStudio/Unity.Systems.CameraProvider), the active camera in Play Mode and Edit Mode
- [Unity.Systems.DependencyInjection](https://github.com/EggyStudio/Unity.Systems.DependencyInjection), attribute-based injection into MonoBehaviours
- [Unity.Systems.EventBus](https://github.com/EggyStudio/Unity.Systems.EventBus), strongly typed event bus
- [Unity.Systems.FieldBinder](https://github.com/EggyStudio/Unity.Systems.FieldBinder), field and property values copied between two objects
- [Unity.Systems.PredefinedAssembly](https://github.com/EggyStudio/Unity.Systems.PredefinedAssembly), types that implement an interface, found across the game assemblies
- [Unity.Systems.RuntimeDiscovery](https://github.com/EggyStudio/Unity.Systems.RuntimeDiscovery), scene discovery and reflection helpers
- [Unity.Systems.SceneLoader](https://github.com/EggyStudio/Unity.Systems.SceneLoader), additive loading of scene groups with progress
- [Unity.Systems.Serializer](https://github.com/EggyStudio/Unity.Systems.Serializer), JSON serialization with atomic file writes
- [Unity.Systems.SettingsDefinition](https://github.com/EggyStudio/Unity.Systems.SettingsDefinition), labels, tooltips, defaults and controls for settings
- [Unity.Systems.SettingsProfile](https://github.com/EggyStudio/Unity.Systems.SettingsProfile), versioned settings profiles in JSON files
- [Unity.Systems.Singleton](https://github.com/EggyStudio/Unity.Systems.Singleton), MonoBehaviour singletons, persistent or not
- [Unity.Systems.SkinnedMeshTransfer](https://github.com/EggyStudio/Unity.Systems.SkinnedMeshTransfer), SkinnedMeshRenderers rebound to another armature by bone name
- [Unity.Systems.Task](https://github.com/EggyStudio/Unity.Systems.Task), allocation-free async and await on the PlayerLoop
- [Unity.Systems.Tick](https://github.com/EggyStudio/Unity.Systems.Tick), actions run at a set number of ticks per second, spread across frames
- [Unity.Systems.Timing](https://github.com/EggyStudio/Unity.Systems.Timing), coroutine scheduler with Update, FixedUpdate, LateUpdate and LazyUpdate segments
- [Unity.Systems.UtilityExtensions](https://github.com/EggyStudio/Unity.Systems.UtilityExtensions), extension methods for cameras, components, vectors, math and audio

### Types
Collections for pooling and reuse.
- [Unity.Types.ManagedArray](https://github.com/EggyStudio/Unity.Types.ManagedArray), pooled, growable array of structs
- [Unity.Types.ObjectPool](https://github.com/EggyStudio/Unity.Types.ObjectPool), thread-safe generic object pools

### UI
Fonts and UI Toolkit components for runtime and editor interfaces.
- [Unity.UI.Fonts](https://github.com/EggyStudio/Unity.UI.Fonts), font families, emoji sprites and TextMeshPro shaders
- [Unity.UI.Toolkit.Animation](https://github.com/EggyStudio/Unity.UI.Toolkit.Animation), USS classes for transitions
- [Unity.UI.Toolkit.ElementLinker](https://github.com/EggyStudio/Unity.UI.Toolkit.ElementLinker), MonoBehaviours bound to VisualElements
- [Unity.UI.Toolkit.Extensions](https://github.com/EggyStudio/Unity.UI.Toolkit.Extensions), extension methods for UIDocument and VisualElement
- [Unity.UI.Toolkit.MarqueeLabel](https://github.com/EggyStudio/Unity.UI.Toolkit.MarqueeLabel), label that scrolls text wider than itself
- [Unity.UI.Toolkit.MenuGenerator](https://github.com/EggyStudio/Unity.UI.Toolkit.MenuGenerator), menus built in an editor TreeView and generated at runtime
- [Unity.UI.Toolkit.ScriptComponents](https://github.com/EggyStudio/Unity.UI.Toolkit.ScriptComponents), MonoBehaviours for events, values, labels and visibility
- [Unity.UI.Toolkit.SplashScreen](https://github.com/EggyStudio/Unity.UI.Toolkit.SplashScreen), animated splash sequence with audio and branding
- [Unity.UI.Toolkit.Tooltip](https://github.com/EggyStudio/Unity.UI.Toolkit.Tooltip), hover tooltips from `VisualElement.tooltip`