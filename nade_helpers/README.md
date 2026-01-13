# Nade Helper Packs

This folder contains **grenade helper packs** for the in-game Nade Helper feature.

## Upload to GitHub
Your cheat downloads packs from:

- **Repo:** `xReev/ReevCheese`
- **Folder:** `nade_helpers/`

So your GitHub repository must contain:

```
nade_helpers/
  de_mirage_T.json
  de_mirage_CT.json
  de_dust2_T.json
  ...
```

## Filename rules (important)
Only files ending in `.json` are listed.

The side shown in the downloader is inferred from the filename:

- `de_map_T.json`  -> T side pack
- `de_map_CT.json` -> CT side pack
- `de_map.json`    -> both sides pack

## JSON schema (must match loader)
Top-level keys:

- `name` (string) recommended
- `map` (string) **required** (example: `de_mirage`)
- `side` (string) optional: `T` / `CT` / anything else = both
- `lineups` (array) **required**

Each lineup requires:

- `id` (string) **required**
- `name` (string) **required**

Optional fields:

- `description` (string)
- `type` (string): `smoke`, `flash`, `molotov`/`fire`, `he`
- `throw` (string): `jump`, `run`, `walk`, `jump_run`, `crouch` (anything else = normal)
- `side` (string): `T` / `CT` (else inherits pack side)

Coordinates / angles:

- `stand_x`, `stand_y`, `stand_z` (player stand position)
- `aim_pitch`, `aim_yaw` (view angles in degrees)
- `dest_x`, `dest_y`, `dest_z` (landing position marker)

## Why these starter packs have 0 coordinates
The reference sites (scope.gg / csnades.gg) do not provide a public API with numeric lineup coordinates.
So the provided packs are **templates** you can fill with real values.

## How to fill coordinates fast (recommended)
In CS2 you can use built-in commands to capture values:

- `getpos` (prints position + angles to console)

Stand on the lineup spot and use `getpos`.

For destination (`dest_*`):
- You can manually set a rough landing marker, or later we can add a small in-game "record landing" tool using your grenade prediction code.
