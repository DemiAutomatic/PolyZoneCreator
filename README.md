# ox_lib Zone Creator

A web map for drawing [ox_lib](https://overextended.dev/ox_lib/Zones/Shared) zones on the GTA V map.

Forked from [skyrossm/PolyZoneCreator](https://github.com/skyrossm/PolyZoneCreator) and converted from PolyZone output to ox_lib / ox_target.

**Live site:** https://demiautomatic.github.io/PolyZoneCreator/

## How to use

1. Draw a **polygon**, **rectangle**, or **circle** on the map.
2. Name the zone when prompted.
3. Click the shape and copy the Lua.
4. Set **Z** and **Thickness / height** in the side panel — the map is 2D, so vertical size is not drawn.

Use **Copy All Lua** to dump every zone currently on the map.

### Draw tools

| Tool | Export |
| --- | --- |
| Polygon | `lib.zones.poly` |
| Rectangle | `lib.zones.box` |
| Circle | `lib.zones.sphere` |
| Marker | `vec3(x, y, z)` |

### Formats

These match ox_lib's in-game `/zone` creator:

- **Function** — `local name = lib.zones.poly({ ... })`
- **Array** — `{ name = "...", points = { ... }, thickness = 4.00 },`
- **Target** — `exports.ox_target:addPolyZone({ ... })`

Check **Export debug = true** to include `debug = true` in the generated table.

## Example

```lua
local pillbox = lib.zones.poly({
	name = "pillbox",
	points = {
		vec3(307.12, -592.44, 30.00),
		vec3(331.08, -580.21, 30.00),
		vec3(339.90, -604.17, 30.00),
	},
	thickness = 4.00,
})
```

## Credits

- Original web tool: [skyrossm](https://github.com/skyrossm)
- Map tiles: [RussianRonin](https://github.com/RussianRonin) via MapTiler Desktop
- Zone API: [overextended/ox_lib](https://github.com/overextended/ox_lib)
