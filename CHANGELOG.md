# Changelog

## v0.1.2 (2026-09-28)

Nothing changes in play.

- Smaller: the development tools are no longer shipped. The mod's scripts are
  about a quarter shorter, and nothing that loads is there for testing only.
- The README carries Jagex's fan content disclaimer.
- A `wp` command given an option it does not have says how to use it.

## v0.1.1 (2026-09-28)

Changed

- **Ctrl+F3** now opens capture mode and **Ctrl+F4** placement mode, the same
  as the panel's CAPTURE and PLACE. They used to capture or place at once,
  with no highlight, preview or levelling, and without pinning or recording
  what they did. Both are listed in Settings > Controls under SHORTCUTS.
- **Esc** is the one key that cancels capture and placement mode (Z is gone).
- **Placement mode levels better on slopes.** It no longer turns red for a
  building the game accepts: floors beside foundations, and foundations held
  by the rest of the structure, are no longer required to touch the ground,
  and props that stand on bare ground set the height when they can. A house
  placed back where it was built now sits at its original height.
- Capture and placement mode do much less work each frame: capture mode no
  longer re-reads every building piece three times a second.
- A first-time panel says what to do: "No blueprints yet: CAPTURE a structure
  to make one."
- After placing, the report reads "Placement complete" (was "Replay
  complete", with pass counts).
- The PLACEMENTS list is one column wide, so each entry shows its full time.
- The capture naming dialog lists the size, then the piece kinds, then asks
  for the name.
- `wp.undo` opens the same removal dialog as PLACEMENTS > REMOVE, for your
  last placement, and `wp.list` opens the panel.

Fixed

- Esc in capture mode also opened the game's pause menu, and could leave
  capture mode running behind it.
- After Esc closed a text box (RENAME, the capture name), N, O and U stopped
  working until another text box was opened.
- Cancelling the capture naming dialog left the game's own hints in place of
  capture mode's.
- When the game paused itself (its window lost focus) with the panel open,
  the panel stopped responding after RESUME. It now closes when the game
  pauses.
- The removal dialog is titled "Remove placement".

Removed

- **Ctrl+F8** (place real pieces in any world, paying for them), Ctrl+F5 (dry
  run), Ctrl+Shift+F4, Ctrl+F12 / Ctrl+Shift+F12, Ctrl+PageUp / Ctrl+PageDown
  and Ctrl+Shift+End. Real pieces are placed with **O** in placement mode, in
  Creative worlds; everything else is in the panel.
- The console commands that duplicated the panel or were test tools:
  `wp.capture`, `wp.replay`, `wp.real`, `wp.dry`, `wp.ping`, `wp.highlight`,
  `wp.hotkey`. `wp` lists the ones that remain.
- An old list window that `wp.list` still opened.

## v0.1.0 (2026-09-26)

First public release. Tested in solo worlds and as a player on a dedicated
server (nothing is installed on the server). Not yet tested with several
players on one server, or in co-op hosted by a player.

- Blueprints panel on **N**, built from the game's own widgets: blueprints in
  two columns, those placed in the current world first (marked with the map
  icon), then by name. A blueprint's tooltip gives its size, when it was
  captured and its pieces by kind (walls, roofs, beams, ...). Clicking one
  selects and pins it; clicking it again unpins it. CAPTURE, REPLAY (in place /
  place), RENAME (Enter confirms; placements follow the new name) and
  PLACEMENTS (remove with confirmation, waypoint, forget); the buttons that act
  on a blueprint or a placement stay dimmed until one is selected. While a
  WildPlans window is open the HUD changes as it does for the game's stations:
  the compass and prompts hide and the footer shows Close [ESC].
- The mod's keys are listed in the game's Settings > Controls, below its own
  key bindings.
- Capture mode: highlights the structure a capture would take; N captures.
- Placement mode: the pinned blueprint as one ghost; rotate, raise and move it
  with the wheel, snap to nearby structure, place as ghosts (N) or as real
  pieces in Creative worlds (O).
- Removing a placement takes it down bottom-up, only the pieces that placement
  put there, and only after a confirmation that re-checks what is standing.
- Blueprints and logs are kept under
  `%LOCALAPPDATA%\RSDragonwilds\Saved\WildPlans\`.
- Console commands under `wp.*`.
