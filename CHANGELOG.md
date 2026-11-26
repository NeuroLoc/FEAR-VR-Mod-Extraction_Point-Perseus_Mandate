# Changelog — F.E.A.R. VR (NeuroLoc)

This document summarizes the **major changes** made to the independent VR project for **F.E.A.R.**, **Extraction Point**, and **Perseus Mandate**.

> **Scope of this changelog:** The project includes hundreds of individual fixes, investigations, and experiments. This document summarizes features and fixes incorporated into the prepared builds; **it is not an exhaustive record of every binary patch or intermediate experiment**. Some smaller early changes were not documented individually after the project was reorganized. Unaccepted experiments and temporary diagnostic builds are not treated as release features.

## [Unreleased]

## [v1.1.0]

- In all three games on GOG and Steam, the default VR layout uses buttons and grip without thumb-rest touch sensors. Tap X to interact, hold X to use a medkit, and press the right stick to open weapon selection. The menu can be bound to a tap, hold, or button combination. <!-- change-id: VR-CONTROLS-STEAM-LAYOUT-MENU-462 -->
- The flashlight can be assigned to a button or combination. By default, squeeze Grip on the off hand at your forehead. A short vibration marks entry into the zone. A custom binding disables the gesture and vibration. A dedicated reset restores the default gesture. <!-- change-id: VR-FLASHLIGHT-BINDING-HAPTICS-461 -->
- The VR settings menus use the same readable font size in Russian and English. Tooltips use a smaller font so their text fits. <!-- change-id: VR-HELP-COMPACT-FONT-466 -->
- Holding Y opens the VR menu by default. Disable this backup in the button layout to reassign Hold Y. Enabling the backup clears the previous Hold Y binding, and restoring the default layout turns the backup on again. <!-- change-id: VR-MENU-BACKUP-Y-468 -->
- The Hold Y backup menu binding also works through SteamVR. In the open menu, the dominant-hand trigger still selects items when assigned to open the menu. <!-- change-id: VR-STEAMVR-MENU-INPUT-469 -->
- VR bindings follow the active OpenXR profile of each hand. Available buttons, stick and trackpad directions, and supported touch inputs can be assigned. Trigger and Grip support taps and holds. The changes were tested on Meta Quest 3. Testing on PICO 4 hardware is pending. <!-- change-id: VR-OPENXR-UNIVERSAL-INPUT-471 -->
- The controller layout has a VR input diagnostics toggle, off by default. When enabled, runtime, controller, and rebinding data go into one VR_Input_Diagnostics.log file capped at 5 MiB. The in-game Help has been updated in English and Russian. <!-- change-id: VR-INPUT-CONTACT-DIAGNOSTICS-472 -->

## [v1.0.0]

### VR Ports and Engine Compatibility

- Fully ported VR functionality to **F.E.A.R. Extraction Point** and **F.E.A.R. Perseus Mandate**, using F.E.A.R. VR 1.3.1 as the original foundation.
- Independently investigated differences in each expansion's `EXE`, `GameClient`, `GameServer`, virtual function tables, object structures, game databases, and engine interfaces.
- Fixed numerous incompatible calls and ABI mismatches across rendering, resources, textures, input, GUI, camera, object handling, databases, and client/server communication.
- Corrected VR startup procedures, loading of required modules, and access to expansion-specific resources.
- Restored correct rendering of VR menus, setup screens, text, prompts, fonts, and UI geometry.
- Corrected camera and FOV issues, including image distortion, incorrect VR rendering, and object positioning problems.
- Fixed numerous level loading problems, story transitions, and failures during scripted sequences.
- Resolved several causes of crashes and failed level transitions in Extraction Point, including address-space exhaustion when moving between large levels.
- Adapted Extraction Point's own save index system instead of referring to the original F.E.A.R. save paths; fixed manual saves, checkpoints, autosaves, and issues restoring level state.
- Made expansion-specific fixes to server-side game logic, game state, save/load behavior, level transitions, and VR interfaces in Perseus Mandate.

### Weapons, Reloading, and VR Interactions

- Fixed deployable turret behavior in **Extraction Point**.
- Fixed the grenade launcher, VES rifle and its scope, and deployable turrets in **Perseus Mandate**.
- Adapted weapons unique to the expansions, including weapon placement, grip alignment, model nodes, firing, ammunition, effects, sound, damage, and VR interactions.
- Extended the **manual VR reload system** for new weapons with different magazines, batteries, bolts, and other weapon-specific components.
- Fixed weapon sights, grabbing interactions, manual reload highlights, and placement of interactive parts. For example, the **Advanced Rifle** required work on its sights, manual reloading, and interaction highlights.
- Restored and tested the **Laser Carbine** in **Perseus Mandate**, including firing, the visible laser beam, sound, ammunition consumption, damage to objects and characters, and manual reloading. These functions were verified in-game.
- Restored the **LP-4 / Chain Lightning Gun** firing behavior in **Perseus Mandate**, including sound, the electrical arc, charge consumption, normal reloading, and damage. **This fix does not claim a separate manual VR reload implementation for the LP-4.**
- Ported and adapted server-side VR logic for physically interactive objects in Perseus Mandate, enabling objects to be picked up, held, carried, and thrown by hand.
- Improved expansion-specific interactions with grenades, mines, and new weapons, including returning objects to the hand.
- Fixed cases where held objects could be incorrectly released, displaced, or mishandled while moving or changing player posture.
- Added an expanded **central holster area** usable with either hand, adapting its behavior for different games.
- Added **physical crouching** based on the player's actual VR height. This was tested in a headset in all three games.
- Adjusted crouching range to make it easier to reach small objects close to the floor. Picking up small floor-level objects was separately confirmed in the original F.E.A.R.; the fix was also ported to both expansions, but separate confirmation of that specific pickup scenario was not recorded for those games.
- Improved player collision with the environment, including preventing unintended auto-stepping onto furniture while retaining normal stair climbing. The behavior was VR-tested and ported to the expansions.
- Improved ladder interactions in **Perseus Mandate**, including grabbing a nearby ladder regardless of viewing direction, entering from above or below, reachability checks, and dedicated English/Russian prompts. The result was tested in VR.

### Cutscenes and Scripted Story Sequences

- Cutscenes that previously appeared on a flat screen can play in stereoscopic 3D VR. Look around freely while the scene follows its scripted camera path. Switch between flat-screen and 3D playback in the in-game VR Options.
- Fixed VR incompatibilities in scripted Perseus Mandate sequences, including camera handling, player movement, and transitions between cutscenes.
- Corrected the sequence involving Alma, the helicopter flight, and the helicopter drop-off, addressing camera-height issues and the transition back to normal control. The corrected sequence was checked in a headset.
- Adjusted when a character appears in the Perseus Mandate introductory cutscene so that unrestricted head movement does not reveal the character too early. Verified in VR.
- Adapted and fixed scripted sequences and 3D cutscenes in Extraction Point.

### Interface, Usability, and Localization

- Added a custom **wrist-mounted Slow-Mo meter** showing the remaining time, including numerical values and support for either hand.
- Made the meter follow the weapon-holding hand, mirrored its display appropriately when switching hands, and added a corresponding VR settings option.
- Added a bilingual **English / Russian** VR interface, translating hundreds of menu strings, prompts, and tutorial cards.
- Added Cyrillic characters to the pixel-style VR font.
- Added a language selection step to the initial VR setup wizard, with immediate persistence of the selected language.
- Added dedicated display names for the expansion ports: **F.E.A.R. Extraction Point VR** and **F.E.A.R. Perseus Mandate VR**, with `v1.0.0` indicated in the interface.
- Separated game configurations and default values for F.E.A.R., Extraction Point, and Perseus Mandate.

### Launchers, Installer, and Distribution

- Developed separate graphical launchers supporting both **VR** and **standard desktop** launch modes.
- Added checks for files and configurations, launch preparation, user-profile backup and restoration, backup history, and safeguards for rolling back changes.
- Prepared one unified **3-in-1** installation package for F.E.A.R. and both expansions. The installer lets users choose which games to modify individually. The package contains only the VR modification files. Install the compatible base game or expansion separately before applying the mod.
- Added installation, reinstallation, updates, removal, file checksum verification, backups, and recovery after failed operations.
- VR opens in a 1280×960 window by default in all three launchers. Saved window settings take precedence. <!-- change-id: VR-FIRST-RUN-DEFAULTS-449 -->
- New profiles in all three games use Auto Pickup by default. Existing profiles keep their saved pickup mode. <!-- change-id: VR-AUTOPICKUP-DEFAULT-456 -->
- In all three games, the Grab Object tutorial appears near selected types of everyday props. Its list uses their physics shapes and applies across levels. <!-- change-id: VR-PROP-ALLOWLIST-455 -->
- The action button works at ladders with empty hands, and alternating Grip remains available for hand climbing. Ladders use one tutorial card, and the Grab Object tutorial yields to cyan interaction hints. <!-- change-id: VR-LADDER-ACTION-453 -->
- Auto Pickup collects eligible items as you approach. Grip & Collect disables proximity pickup. Both modes let you grab and carry items by hand. <!-- change-id: VR-PICKUP-MODES-451 -->
- Added an Information window with NeuroLoc's contact details to each launcher. The shared installer log is scrollable and shows a green message when all selected installations succeed. Installation was tested on GOG and Steam test setups. <!-- change-id: LAUNCHER-INFORMATION-445 -->
- The uninstaller removes logs, VR launcher settings, and other mod leftovers, preserves game saves and third-party plugins, and restores a verified original EXE after an LAA change when needed. The report lists what was removed and restored. Tested on GOG and Steam test setups for all three games. <!-- change-id: UNINSTALL-CLEANUP-446 -->
- Prepared separate default game settings. Personal saves, profiles, and tutorial progress are not included in the distributed package.
- Added short **English and Russian** player guides covering installation, launch, controls, calibration, picking up objects, and removal.
- Combined support for compatible **GOG and Steam** releases into the game-specific components of the unified package. Original game executables are not redistributed.
- Adjusted handling of Steam warnings for installed executable checksum mismatches while preserving checksums for the modification's own files.
- Added automatic **Large Address Aware (LAA)** preparation for Extraction Point and Perseus Mandate on VR launch, with backups before executable changes. This addresses confirmed out-of-memory failures in relevant scenarios.
- Disabled automatic LAA modification for the **original Steam version of F.E.A.R.**, since the tested Steam build rejects the modified executable. The stock GOG executable for the original game was verified to have LAA enabled. The installer provides a separate notice about these differences.
- Preserved patch maps, SHA-256 hashes, manifests, source code for custom plugins, installation tests, and rollback procedures. These are internal development records and may not all be included in the public download.

### Testing and Verification

- **NeuroLoc played all three campaigns from start to finish in VR**: F.E.A.R., Extraction Point, and Perseus Mandate. Some campaigns were completed more than once. Cutscene and gameplay issues encountered during those playthroughs were fixed and the affected sequences were retested in VR.
- Verified VR startup on Steam releases. Required ASI plugins were observed loading in Extraction Point and Perseus Mandate, alongside the VR components of the original game.
- Tested installation, updates, removal, and rollback for selected games within the unified **3-in-1** package.
- Preserved checksums, change maps, and individual VR test confirmations for a substantial number of fixes.

### Known Behaviors and Limitations

- The project is **not based on later releases of F.E.A.R. VR**. Its original foundation is **version 1.3.1**, with subsequent expansion-port development carried out separately.
- Not all features are identical across all three games; the expansions have their own unique mechanics.
- LAA cannot be enabled automatically for the original Steam F.E.A.R. in the same way as for the expansions. This is a limitation of the tested stock executable, not a prohibition on VR launch.
- The historical record does not cover every small fix. Some features ported between games have not received separate headset verification for every individual scenario.
- Further updates may include bug fixes, compatibility improvements, or new features. No fixed update schedule or scope of future releases is promised.

---

**Expansion ports and subsequent development:** NeuroLoc. For project origins, publication permission, and technical support responsibilities, see [`README.md`](README.md).
