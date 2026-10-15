# Realmbound v0.2.0

Owner-approved playable Windows release, October 15, 2026. This promotes the
tested Candidate 3 runtime without gameplay changes. It is still an unsigned,
early prototype, built with UE 5.8.3 in Win64 **Development**, not Shipping.

## Download and launch

[Get Realmbound-v0.2.0-Win64.zip](https://github.com/komatosekoala/Realmbound-Downloads/releases/tag/v0.2.0)
under Assets. Extract the entire ZIP, then run **Windows/Realmbound.exe**.
Do not run inside the ZIP or download the automatic Source code archives to play.
No Unreal Engine or Blender installation is needed. See [HOW_TO_PLAY](HOW_TO_PLAY.md).

## In this release

- Three classes, five mouse-driven combat inputs, five waves and the Rift Sentinel.
- Personal walk-over loot; every collected gear affix stacks for the run.
- Three Legendary mechanics per class, all distinct in each pedestal offer;
  random enemy Legendaries supplement the chosen pedestal rewards.
- Ordinary drop chances: **12% gear**, independently **16% run items**.
  Fifteen percent of gear rolls are Legendary. Item strength and enemy tuning
  are unchanged from Candidate 3; more drops mean more player power.
- Shadowy slate-grey wall tint restored; seamed floor and Rift sky retained.
  Tear, sky crystal clusters/towers and decorative floor plates remain removed.
- Native textured UI, adjustable HUD, settings, procedural combat audio,
  server-owned run statistics and a party damage meter.

## Co-op

Everyone uses the same v0.2.0 ZIP. Host a room, then friends Join by IP using the
host's reachable IPv4 address, normally port7777. Internet hosting requires
reachable **UDP7777**. Localhost/127.0.0.1 only connects to the same PC.
There is no relay, matchmaking, automatic NAT traversal or host migration.

## Verification and known limits

Fresh Editor/Game compilation, cook/package, **86 automation tests** (81 clean,
five existing warning groups), two navigation seeds and host-plus-two-client
session/menu/disconnect/quit flow passed. One staged packaged gameplay-camera
frame was inspected. Runtime files are byte-identical to tested Candidate 3.

**Known issue:** an earlier full scripted co-op run stalled at the first boss
gold-ring objective at6600HP. Bot pathing versus gameplay defect is unresolved.
This release does not claim a new full-run clear, mortal balance trial, WAN
verification or four-PC performance result. Current item forecasts assume100%
collection; drops expire120s after spawning and have no automatic sweep.

Host-only Development commands remain available; remote cheat requests are
rejected. Source stays private. The public download contains only this current
runtime and play instructions—no older builds, source, personal settings or logs.
