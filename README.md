# CS2 Configs by 1EF

Personal Counter-Strike 2 client settings and separately selected practice, demo-review and experimental configurations.

Public profile: https://settings.gg/1ef_official

## Current client profile

`autoexec.cfg` contains the reviewed client preferences and key bindings saved on 15 November 2026:

- Mouse sensitivity `0.8`; viewmodel FOV `68`, offsets `2 / 2 / -2`.
- Crosshair style `5`, RGB `92 / 250 / 50`, opacity `255`, length `2`, thickness `1`, gap `1`, no outline, no dot and follow recoil disabled. Pixel scaling uses the saved reference height of `1440`.
- Radar HUD scale `0.8`, map scale `0.35`, rotation disabled and teammate colours `1`.
- F1 selects molotov/incendiary, F2 smoke, F3 flashbang and F4 HE grenade. SHIFT uses `+sprint`; mouse-wheel up/down jump.
- I toggles crosshair length between `2` and `255`. H uses the existing bomb-drop alias; P and K are noclip and grenade-rethrow shortcuts for an appropriate local/practice context.
- FPS limits retain the saved unlimited values. This is a personal profile, not a measured performance guarantee.

The autoexec applies its listed preferences and bindings, then calls `host_writeconfig`. It preserves unlisted keys and clears only explicitly listed unbound keys. Back up existing settings before loading it. If you change preferences in the game, update the corresponding autoexec entries before reloading the profile.

Display mode, resolution, refresh rate and anti-aliasing remain in the separate `cs2_video.txt` file. The autoexec does not select a display backend, set a Windows audio-device identifier, or change Steam launch options. Server/debug boilerplate and cached UI activity markers are excluded from the personal autoexec.

## Configurations

| File | Purpose |
| --- | --- |
| `autoexec.cfg` | Current personal client preferences, aliases and bindings. |
| `autoexec_nades.cfg` | Local grenade practice: cheat-gated settings, purchases, long rounds, impacts, bot removal and a restart. |
| `autoexec_bunnyhop.cfg` | Cheat-enabled local movement and bunnyhop practice. |
| `autoexec_demoui.cfg` | Demo-review helper with demo UI, fog/FOV overrides and a reduced HUD. Current-build support and demo/server context matter. |
| `autoexec_troll_crosshair.cfg` | Separate experimental style `9` crosshair with oversized pixel settings and the magenta theme. Run `exec autoexec` to restore the personal profile. |

The experimental crosshair uses current pixel-setting names (`cl_crosshair_length`, `cl_crosshair_thickness`, `cl_crosshair_gap`, `cl_crosshaircolor_a` and explicit outline colour channels). Its `1080` reference height controls crosshair scaling; it does not set display resolution. The helper migration is source-checked; its final appearance has not been verified in-game.

## Reviewed saved settings

The [saved-settings snapshot](snapshots/cs2/README.md) contains the reviewed configuration files saved on 15 November 2026. It supersedes the older uploaded ZIP for current-profile use. Private challenge/device entries, cached activity markers and saved launch-state data are omitted from the machine-settings copy. Original local files remain outside this public repository.

The video snapshot stores **1920×1440 (4:3), Fullscreen Windowed and CMAA2**, with MSAA and VSync disabled. It does not claim that a custom 5:4 mode is selectable in the game's menu. Review display and hardware fields before restoring a video snapshot on another system.

For a settings-sharing service, the main files are the reviewed copies of `cs2_machine_convars.vcfg`, `cs2_user_convars_0_slot0.vcfg`, `cs2_user_keys_0_slot0.vcfg`, `cs2_video.txt`, plus the maintained root `autoexec.cfg`. The three additional key-slot files are empty configuration objects preserved for completeness.

## Installation and use

Clone the repository:

```sh
git clone https://github.com/jikovec/CS2.git
```

Copy only the chosen root `.cfg` files to the game's configuration directory:

- Windows example: `C:\Program Files (x86)\Steam\steamapps\common\Counter-Strike Global Offensive\game\csgo\cfg`.
- Linux: `<Steam library>/steamapps/common/Counter-Strike Global Offensive/game/csgo/cfg/`.

Saved `.vcfg` and video settings belong separately under Steam's `userdata/<account>/730/local/cfg/` directory. Close the game and back up the matching installed files before restoring selected snapshots. Do not copy the whole snapshot directory into the executable-config location or run a `.vcfg`/video snapshot using `exec`.

In the CS2 developer console, load one selected root configuration:

```text
exec autoexec
exec autoexec_nades
exec autoexec_bunnyhop
exec autoexec_demoui
exec autoexec_troll_crosshair
```

The last four are separate choices, not startup dependencies. Practice helpers may enable local-server cheats and are not instructions for competitive servers. Aliases and server-context shortcuts still need appropriate gameplay testing.

## Validation boundaries

An earlier revision of the personal profile was executed in the installed Linux client: owner-provided console output reached `loaded 1EF` without reported unknown-command or rejected-setting messages, and user-config saves succeeded. A subsequent comparison preserved the selected values, bindings and video file. Later colour, sensitivity and teammate-colour updates were reconciled against the final saved settings; do not treat that earlier transcript as execution proof for every byte of the final revision.

Final source checks compare the personal autoexec with the saved selections, verify binding completeness and uniqueness, check the reviewed snapshot structure and privacy omissions, preserve historical files and recorded line endings, and check Git whitespace and the publication allowlist. The repository has no configured CI workflow. Static name checks are not proof of command behaviour, visual correctness, performance or helper acceptance in-game.

## Public scope and historical configurations

Only reviewed configuration/profile files are published. Private photos, videos, demos, account data, credentials, raw exports and unrelated personal files remain outside the repository. The deny-by-default ignore rules allow only named reviewed paths.

`legacy/csgo/` preserves historical CS:GO configurations unchanged. They must not be installed as current CS2 settings. The root personal profile and final saved snapshots use LF; the four helper configs retain their existing CRLF line endings and final-line conventions.

Source publication is distinct from an installed-game change or in-game acceptance.
