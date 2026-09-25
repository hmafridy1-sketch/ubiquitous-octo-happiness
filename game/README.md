# Coffee Courier Planet — prototype

A modular single-player 3D browser-game prototype.

## Play

Open `game/index.html` in a browser. The prototype uses Three.js from a pinned CDN URL and needs an internet connection when first loading.

Controls:
- Desktop: WASD / arrow keys to walk, Space to deliver.
- Mobile: on-screen joystick + DELIVER button.

## Architecture

- `game/index.html` contains the first playable vertical slice.
- World placement is data-driven through latitude/longitude definitions.
- `pet()` is the modular pet factory for the courier and neighbors.
- `makeCup()` builds the visible carried coffees.
- Delivery state is isolated from movement and rendering so mechanics can be replaced later.

## Blender-ready asset plan

The runtime intentionally keeps geometry simple so future Blender `.glb` assets can replace the procedural meshes without changing gameplay code. Recommended asset slots:
- `assets/codex-courier.glb`
- `assets/pets/*.glb`
- `assets/cafe.glb`
- `assets/town/*.glb`
- `assets/props/*.glb`

Use low-poly meshes, baked/packed textures, and a small number of materials for browser performance. The next iteration can add `GLTFLoader` and swap these assets into the same named scene nodes.

## Next iteration targets

1. Replace procedural pets/buildings with editable Blender GLB assets.
2. Add richer spherical path networks and actual stair/bridge traversal.
3. Add small discovery interactions and delivery animations.
4. Add round timer, scoring and optional photo-mode.
5. Add asset-loading fallback so the game remains playable when a GLB is unavailable.
