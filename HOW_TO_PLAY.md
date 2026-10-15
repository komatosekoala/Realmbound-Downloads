# Realmbound v0.2.0 — how to play

## Install

1. Open [the v0.2.0 release](https://github.com/komatosekoala/Realmbound-Downloads/releases/tag/v0.2.0).
2. Under **Assets**, download **Realmbound-v0.2.0-Win64.zip**. GitHub's automatically generated “Source code” archives are NOT the playable game.
3. Right-click the downloaded ZIP → **Extract All** into a new folder.
4. Run **Windows/Realmbound.exe** from the extracted folder. Keep the Engine, Realmbound and all other folders together.

Do not open the EXE while browsing inside the ZIP. That can cause “CreateProcess() returned 2” because required files were not extracted. Windows x64 is required; Unreal Engine and Blender are not.

If Microsoft runtime components are missing, run the included **Windows/Engine/Extras/Redist/en-us/vc_redist.x64.exe**. The executable is unsigned; no code-signing or security-warning bypass is provided.

In the development checkout, **PLAY_REALMBOUND.cmd** launches the finalized local package at **Builds/Realmbound-v0.2.0-Win64/Windows/Realmbound.exe**. A fresh source clone has no generated Builds folder; download the release or build/package first.

## Solo and co-op

Choose a class, then **SOLO**. Survive five waves and defeat the boss. Death sidelines a player until the next wave; a party wipe ends the run. Results and Escape menus let you replay, return to the main menu or quit.

To host:

1. Everyone installs this same v0.2.0 ZIP.
2. Choose a class and Normal, Hard or Brutal, then **Host**.
3. Friends choose **Join by IP**, enter your reachable IPv4 address and port, then connect.
4. Wait for the party before starting the run. The host can use F5.

On a LAN use the host PC's LAN IPv4 address, usually with port **7777**. Across the internet, the host needs reachable **UDP 7777**, suitable routing/firewall rules, or an already configured shared virtual LAN. This game does not configure any of that. Carrier-grade NAT can prevent direct hosting.

**127.0.0.1 and localhost mean the joining player's own PC. They do not connect to a friend's PC.** The game remembers the last successfully joined address; the field is editable. IPv4 with optional port and localhost are supported, not IPv6 or general hostnames.

There is no relay, matchmaking, NAT traversal or host migration. Local host/client tests do not prove WAN reachability. If the host leaves, clients return to the menu with a connection-ended message. A late join can wait until the next wave or run to revive.

## Controls

| Input | Action |
| --- | --- |
| Mouse | Continuous free-look aiming |
| WASD / Space | Camera-relative movement / jump |
| Left click, hold to repeat | Primary |
| Right click | Stronger secondary |
| Shift | Mobility; interrupts attack motion |
| 1 | Self-heal |
| R | Ultimate |
| Mouse wheel | Camera distance |
| Hold Tab | Release cursor to inspect item/ability icons |
| I or F7 | Read-only inventory and stats |
| F6 | Toggle the party damage meter |
| Escape | Resume, Inventory, Settings, Leave Run, Quit |
| F10 | Settings |
| F1 / F2 / F3 | Warrior / Mage / Hunter between runs |
| F5 | Host starts or restarts |
| Tilde | Development console |

No mouse-button steering or old five-number-key attack layout remains. Aim under the crosshair; cover can block a shot even when the camera sees the target. A blocked crosshair indicates muzzle obstruction.

Escape/settings pause standalone SOLO. Hosted games continue for everyone, even if the host opens a menu. Tab and inventory inspection do not make a multiplayer session safe.

## Classes and resources

| Class | Play style | Starting health | Resource |
| --- | --- | ---: | --- |
| Warrior | Sword, plate, close-range attacks | 180 | Earned rage; starts at 8, no passive combat regen |
| Mage | Staff bolts and magic | 90 | Mana, baseline 9/s |
| Hunter | Bow and mobile ranged attacks | 125 | Energy, baseline 18/s |

All secondaries have a **3-second base cooldown**. All heals have a **20-second base cooldown**. Item effects can change actual cooldowns and costs; the inventory/stats view shows current totals.

Ultimates cost **40% / 50% / 80%** of maximum resource for Warrior / Mage / Hunter, with baseline cooldowns **50 / 55 / 50 seconds**. Warrior's primary is admitted at zero rage and pays 1.5 only after positive applied damage. Rage is earned from damage; its decay floor does not replenish a resource below that floor.

## Loot and the pedestal

Walk over your own drops to collect them. **Every collected gear copy contributes for the run. There are no equip slots or manual replacement choices.** The chest/glove/leg/weapon shapes are visual categories, not inventory restrictions.

Ordinary kills make independent personal server rolls:

- **12% gear**, Common or Legendary.
- **16% stacking run item**.
- **15% of gear rolls** are random Legendaries: 1.8% of ordinary kills overall.

Both rolls can succeed on one kill. The rates imply 126 random drops over 450 ordinary kills on average, not a guaranteed inventory. The estimates assume **100% collection**. Drops expire after **120 seconds**, pickup range is **210 cm**, and there is no magnet or automatic wave-end sweep.

Each completed wave gives a separate Slipstream biscuit and a personal **one-of-three Legendary pedestal choice**. Approach the bridge pedestal during the breather. Its three offers have distinct class mechanics. Choose health-focused affixes if your random drops left you fragile. The boss guarantees a random Legendary. Repeated mechanics unlock once; every copy's affixes still stack.

The permanent top bar shows collected item types and counts. Hold Tab for descriptions; I/F7 shows names, effects and current totals. There is no F8 behavior-tool choice: Pocket undertow, Backfire spool and Mercy bell now use ordinary run-item acquisition.

### Legendary mechanics

| Class | Mechanics |
| --- | --- |
| Warrior | Bloodbound: lifesteal from applied attack damage. Seismic: third-attack nearby nova. Reprisal: Charge grants a short frontal parry; a successful parry readies a free fast secondary counter. |
| Mage | Overflow: high-mana attack bonus. Echo: third-spell impact burst. Afterimage: Blink leaves a short-lived echo that fires weaker primary bolts from the old position. |
| Hunter | Quickdraw: cheaper/faster primary, subject to the server rate floor. Ricochet: additional nearby visible target. Threadneedle: primary pierces one additional enemy for a reduced second hit; cover/shields stop it. |

### Run items

Ember tooth (damage), Heartstone (max health), Wind feather (movement), Source bead (resource), Clock shard (cooldowns), Life bloom (self-heal), Iron charm (armor), Keen lens (critical chance), Slipstream biscuit (short primary-damage window after mobility), Pocket undertow (secondary pull), Backfire spool (mobility aftershock), Mercy bell (heal-created ally ward).

The item panel gives exact current totals. Main-stat diminishing returns and caps still apply, but offensive surplus grows with additional items and requires confirmed, unobstructed hits. It cannot recurse or bypass shields. All numerical tuning is in **Content/Tuning/Combat.json**; the server controls gameplay.

## Settings

Use Escape → Settings or F10. Display mode, resolution, sensitivity, invert-Y, volume/mute, graphics and movement preferences are saved locally.

HUD size is a live **50–125% slider**, default **85%** for new preferences. Menus remain independently readable. Frame caps are **60 / 120 / 144 / 180 / Uncapped**, with VSync; fresh preferences default to **180, VSync off**. A cap is not a performance guarantee.

Run progress/items are not saved. Only settings and the successful join address persist.

## Boss and warnings

Ground telegraphs must be dodged laterally; jumping does not escape them. The boss has aimed cannon pressure, predicted ground eruptions and rally attacks, plus changed phase-two behavior. At health thresholds the gold-ring objective requires surviving players to align together before damage resumes.

**Known issue:** a previous host-plus-two-client scripted full run stalled at the first gold-ring objective at 6600 HP. Whether that is bot navigation or a gameplay defect is unresolved. The latest package passed targeted checks, not a new full-run clear or mortal balance trial.

## Development commands

This finalized GitHub release uses the tested **Win64 Development** binaries, not a new Shipping build. These commands are restricted to the local authoritative host; remote requests are rejected:

```text
RbGiveItem 0 3
RbGiveRarity Common 0
RbGiveRarity Legendary 3
RbGiveResource 100
RbKillAll
RbSkipWave
RbGod
RbSpawnBoss
```

Gear appearance indices are 0 chest, 1 gloves, 2 legs, 3 main hand, 4 off hand. They do not recreate equip slots. Developer commands invalidate ordinary balance observations.

## Verified and unverified

Fresh Candidate 3 Editor/Game builds, cook/package, 86 automation tests (81 clean, five existing warning groups), navigation on seeds 1701 and 8123, host-plus-two-client menu/session/leave/quit flow, and one staged packaged gameplay-camera frame passed. The release runtime is byte-identical to Candidate 3.

This is an early prototype. No new full-run clear, mortal trial, four-PC performance result, internet-connectivity guarantee or signed executable is claimed.
