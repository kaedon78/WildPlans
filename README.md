# WildPlans

[![Latest release](https://img.shields.io/github/v/release/kaedon78/WildPlans)](https://github.com/kaedon78/WildPlans/releases/latest)
[![Game: RuneScape: Dragonwilds](https://img.shields.io/badge/game-RuneScape%3A%20Dragonwilds-orange)](https://store.steampowered.com/app/1374490/)
[![Requires UE4SS 3.0.1](https://img.shields.io/badge/requires-UE4SS%203.0.1-blueviolet)](https://www.nexusmods.com/runescapedragonwilds/mods/4)
[![License: MIT](https://img.shields.io/badge/license-MIT-blue)](LICENSE)

Blueprints for **RuneScape: Dragonwilds**.
Save a building you have made, then place it again somewhere else as the
game's own ghost pieces, and build it up piece by piece or all at once.

- **Capture** any player-built building into a blueprint, with a name.
- **Place** a blueprint as a single ghost that you can turn, raise and move
  before you set it down.
- **Rebuild in place** exactly where the blueprint was captured, as a backup
  and restore.
- **Undo** a placement from the list of everywhere a blueprint has been
  placed.

Everything is done from one in-game panel. It uses the game's own menus,
icons and dialogs, so there are no files to edit.

> Early release (v0.1). Tested in solo worlds and as a player on a dedicated
> server. Not yet tested with several players on one server, or in co-op hosted
> by a player.

*Created using intellectual property belonging to Jagex Limited under the terms
of Jagex's [Fan Content Policy](https://legal.jagex.com/docs/policies/fan-content-policy).
This content is not endorsed by or affiliated with Jagex.*

## Install

1. Install **UE4SS v3.0.1** for Dragonwilds
   ([UE4SS for RSDragonwilds on Nexus](https://www.nexusmods.com/runescapedragonwilds/mods/4)).
2. Download `WildPlans-vX.Y.Z.zip` from
   [Releases](../../releases) and unzip it into
   `...\steamapps\common\RSDragonwilds\RSDragonwilds\Binaries\Win64\ue4ss\Mods\`
   so that you get `Mods\WildPlans\Scripts\main.lua`.
3. Start the game. The `enabled.txt` in the folder turns the mod on. If your
   UE4SS uses `Mods\mods.txt` instead, add the line `WildPlans : 1` above the
   `Keybinds` line.

When the mod has loaded, a gold house icon with an **N** under it appears in
the bottom-right strip of the HUD.

To uninstall, delete `Mods\WildPlans`. Your blueprints stay where they are
(see below).

## Use

Press **N** to open the **blueprints panel**. It lists every blueprint with
its piece count, those placed in the current world first (marked with the map
icon); hover one for its details. Clicking a row **pins** that blueprint (the
gold one) and the buttons along the bottom act on it; clicking it again unpins
it.

| Button | Does |
|---|---|
| **CAPTURE** | Enters capture mode: the structure nearest you (within 100 m) is highlighted. **N** captures it and asks for a name; **Esc** cancels. |
| **REPLAY** | **IN PLACE** lays ghosts exactly where the blueprint was captured. **PLACE** enters placement mode (below). |
| **RENAME** | Renames the blueprint (**Enter** confirms). Its placements keep up with the new name. |
| **PLACEMENTS** | Lists everywhere this blueprint stands in the current world, with **REMOVE** (shows what will go and asks you to **CONFIRM**), **WAYPOINT** (marks it on your compass) and **FORGET** for each. |

**Esc** or **N** closes the panel. The mod's keys are also listed in the
game's **Settings > Controls**, below its own key bindings.

**Placement mode** shows the pinned blueprint as one ghost in front of you:

| Key | Does |
|---|---|
| mouse wheel | rotate 15° (90° with snap on) |
| `Ctrl` + wheel | up / down 15 cm |
| `Alt` + wheel | forward / back 150 cm |
| `U` | snap to nearby structure on / off |
| `N` | place it as **ghosts**, free, for you to build from the build menu |
| `O` | place it as **real** pieces: **Creative worlds only** |
| `Esc` | cancel |

Ghosts cost nothing and cannot half-finish, so it is safe to try a spot, walk
round it, and remove it (**PLACEMENTS** > **REMOVE**) if you don't like it.

### Where your blueprints are

`%LOCALAPPDATA%\RSDragonwilds\Saved\WildPlans\`

- `blueprints\`: one `.wplan` file per blueprint, plain text. Share one by
  copying the file.
- `blueprints\placements.txt`: where each blueprint has been placed, used by
  PLACEMENTS.
- `logs\`: what the mod did. Attach these (and `ue4ss\UE4SS.log`) to a bug
  report.

### Keys and console commands (optional)

The panel covers everything, so you don't need these. They are there for
anyone who prefers them:

| Key | Does |
|---|---|
| `Ctrl+F3` | capture mode (the panel's **CAPTURE**) |
| `Ctrl+F4` | placement mode for the pinned blueprint (**REPLAY** > **PLACE**) |

With the UE4SS GUI console enabled (`GuiConsoleEnabled = 1` in
`UE4SS-settings.ini`; `Ctrl+O` opens it), type `wp` for the list of commands:
`wp.panel`, `wp.list`, `wp.rename`, `wp.capturemode`, `wp.placemode`,
`wp.inplace`, `wp.undo` (removes the last placement, asking first) and
`wp.close`. Each does what its panel button does.

## Limits

- **Only player building pieces** are captured. The game's world props and
  terrain are not.
- **Real placement:** `O` works in Creative worlds only. Elsewhere, place
  ghosts and build them from the build menu as normal.
- **Game updates** can change piece data. If the panel or placement stops
  working after a patch, check for a new WildPlans release.
- **Servers:** the mod runs on your client only; nothing is installed on the
  server. On a dedicated server everything above works (tested: capture, ghost
  and real placement, a 464-piece placement, undo, and all of it again after a
  server restart). Two things differ from solo: undo and IN PLACE only see
  pieces near you, and the server saves every 5 minutes, so something placed
  just before a server restart can be lost.
- **Several servers:** the mod cannot tell servers apart, so PLACEMENTS shows
  the placements you made on all of them. Removing one only removes pieces that
  match it exactly, piece by piece and position by position, and asks first.
- **Not yet tested:** several players building on one server, and co-op
  hosted by a player.

## License

MIT. See [LICENSE](LICENSE). RuneScape: Dragonwilds is © Jagex. This is an
unofficial fan mod and ships none of the game's assets.
