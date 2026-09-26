# Changelog

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
