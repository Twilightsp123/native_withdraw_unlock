# Native Withdraw Unlock v1.1.2 — Installation (English)

**Release status:** Official stable v1.1.2, confirmed tested in-game by the author.  
**Game:** Total War: WARHAMMER III, **Windows x64**.  
**Mandatory dependency:** Cpecific's Memreader (win64), exposing `_G.memreader`.

## Required files

- `native_withdraw_unlock.pack` — extract it from this repository's `dist/native_withdraw_unlock_v1.1.2.zip`.
- `twwh3-memreader.pack` — Cpecific's Memreader. The provided `twwh3-memreader.zip` contains this pack. Original Steam Workshop listing: https://steamcommunity.com/sharedfiles/filedetails/?id=2789863945

Do not assume that the separate **memreader Plus** mod is a drop-in replacement without verifying API compatibility.

## Installation steps

1. In Steam, right-click **Total War: WARHAMMER III** → **Manage** → **Browse local files** to find the game folder.
2. Download the v1.1.2 ZIP and **extract** `native_withdraw_unlock.pack`; do not place the ZIP itself in the game folder.
3. Either subscribe to and enable Cpecific's Memreader via Steam Workshop, or extract `twwh3-memreader.pack` from your existing dependency archive.
4. Copy `native_withdraw_unlock.pack` into the game's `data` folder. If installing Memreader manually, copy `twwh3-memreader.pack` into that same `data` folder.
5. Enable both mods using a mod manager that supports local pack files. Avoid enabling duplicate Memreader copies.
6. Start a battle, **leave Deployment by pressing Start Battle**, select a unit, and use the game's original **Withdraw** command.

Example folder (yours may differ): `C:\Program Files (x86)\Steam\steamapps\common\Total War WARHAMMER III\data\`.

## If your local pack is missing from the launcher

Some CA launcher / mod manager versions do not display locally installed packs the same way as Workshop subscriptions. Use a manager that explicitly supports local .pack imports. Advanced users may also use `user.script.txt` after backing it up, but avoid double-loading packs.

Typical path: `%APPDATA%\The Creative Assembly\Warhammer3\scripts\user.script.txt`.

If **both** packs are managed manually, an example is:

```txt
mod "twwh3-memreader.pack";
mod "native_withdraw_unlock.pack";
```

Do not also list a Workshop-managed Memreader if it is already active.

## Troubleshooting, compatibility and removal

- This unlocks **native per-unit battle withdrawal**, not campaign strategic Retreat, morale routing, teleportation or custom scripted movement.
- Confirm the dependency is enabled; the script requires global `_G.memreader`.
- Test after battle deployment, not during pre-battle deployment. Check for other mods changing the battle UI.
- Diagnostic logging is disabled by default in v1.1.2.
- This mod changes process memory, not the on-disk EXE; native offsets are game-build-specific. A game update may require an updated mod.
- To uninstall, disable/remove the Withdraw Unlock pack; keep Memreader if another mod still requires it.

## Release note

The author has explicitly confirmed that **v1.1.2 is the official tested release**. Some archived technical text inside the pack still calls it a candidate / unverified; this is stale historical wording, not the present release status.

Cpecific owns the third-party Memreader dependency. This repository links to the original mod rather than redistributing its binary package.
