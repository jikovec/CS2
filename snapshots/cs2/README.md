# Reviewed CS2 saved settings

Current saved-setting files reviewed on **15 November 2026**. These files replace the older ZIP-derived snapshot for current-profile use. The original ZIP and private pre-change backups remain outside the repository.

| File | Contents |
| --- | --- |
| `cs2_machine_convars.vcfg` | Current machine/client variables, sanitized as described below. |
| `cs2_user_convars_0_slot0.vcfg` | Current crosshair, sensitivity `0.8`, viewmodel and user preferences; the public name is `1EF`. |
| `cs2_user_keys_0_slot0.vcfg` | Current keyboard, mouse and analog bindings. |
| `cs2_user_keys_0_slot1.vcfg` | Empty saved configuration object. |
| `cs2_user_keys_0_slot2.vcfg` | Empty saved configuration object. |
| `cs2_user_keys_0_slot3.vcfg` | Empty saved configuration object. |
| `cs2_video.txt` | Saved 1920×1440 Fullscreen Windowed video settings, CMAA2 enabled, MSAA/VSync disabled; includes source hardware/display metadata. |

## Privacy and preservation

Six files retain the final local source bytes. The machine-convars copy retains its formatting and values except for these eight omitted entries:

- `ui_playsettings_directchallengekey`: private challenge value.
- `voice_device_override`: local audio-input device selection.
- `cachedvalue_count_partybrowser`, `cachedvalue_count_teammates`, `cl_promoted_settings_acknowledged`, `cl_redemption_reset_timestamp` and `ui_news_last_read_link`: cached activity or UI state.
- `trusted_launch`: saved launch state, not a portable preference to distribute or replay.

A sound-device override was absent from this source; it is not introduced. Current LF line endings are preserved. This is a sanitized settings snapshot, not a complete account backup.

## Relationship to the autoexec

The maintained root `autoexec.cfg` applies the selected personal client preferences and bindings. Reloading it can overwrite overlapping preferences edited later in the game, and `host_writeconfig` persists the result.

The current crosshair is style `5`, RGB `92 / 250 / 50`, alpha `255`, length `2`, thickness `1`, gap `1`, no outline/dot and follow recoil disabled, with a saved `1440`-pixel reference height. The I binding toggles length `2 / 255`.

The binding snapshot references `+dropc4`; its alias definition lives in the root autoexec. A saved key file does not contain that alias definition. The experimental crosshair remains a separate manual choice.

## Restoration and validation

Close CS2, back up the corresponding installed files and identify the matching Steam `userdata/<account>/730/local/cfg/` directory before restoring selected snapshots. Review hardware IDs, monitor index, supported display modes and graphics preferences before using the video file on another machine. These files are not console scripts and must not be loaded using `exec`.

Source comparisons verify the selected profile values and bindings and account for the exact sanitization above. An earlier personal-autoexec revision loaded cleanly in the owner's Linux client. Final preference updates and the helper migration have source evidence; they do not establish fresh visual/gameplay acceptance for every configuration.
