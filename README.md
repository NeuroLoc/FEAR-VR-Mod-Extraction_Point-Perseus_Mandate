# F.E.A.R. VR — An Independent Project by NeuroLoc

> **NeuroLoc release:** `v1.0.0`

[Русская версия](README_RU.md)

**An unofficial VR modification for F.E.A.R., F.E.A.R. Extraction Point, and F.E.A.R. Perseus Mandate.**

Developed by **NeuroLoc**, this project brings VR support to both F.E.A.R. expansions and includes an extensively modified VR version of the original game.

The project includes hundreds of fixes and improvements involving reverse engineering, engine interface adaptations, debugging, testing, and the development of additional VR features.

## Supported Games

- **F.E.A.R.**
- **F.E.A.R. Extraction Point**
- **F.E.A.R. Perseus Mandate**

Compatible **GOG** and **Steam** releases are supported. Some behavior depends on the specific game version; see **Important Compatibility Notes** below.

The project is distributed as **one 3-in-1 package** containing the VR modifications for all three games. The installer lets you choose which of your installed games to modify; you do not have to install the VR mod for all three.

## Main Features and Improvements

The project includes hundreds of changes, including:

- VR ports for Extraction Point and Perseus Mandate.
- Engine compatibility fixes involving rendering, the camera, field of view (FOV), menus, and the HUD.
- Support for expansion-specific weapons and improvements to manual VR reloading.
- Fixes to physical object grabbing, hand interactions, and the holster system.
- Physical crouching and improved interaction with objects near floor level.
- Player collision fixes involving the environment.
- Improved VR ladder interaction in Perseus Mandate.
- A custom wrist-mounted Slow-Mo meter.
- A bilingual VR interface in English and Russian.
- Separate settings and user profiles for each game.
- Dedicated launchers with VR and standard desktop launch modes.
- Memory, save/load, level loading, and story transition fixes.
- A unified installer with backups, updates, removal, and file verification.

Some features and fixes apply only to specific games. This is a summary, not a complete list. For details, see [`CHANGELOG.md`](CHANGELOG.md).

## Requirements and Installation

**You will need:**

- An installed, compatible PC version of the game you want to play.
- A VR headset and a compatible **OpenXR runtime**.
- The unified **3-in-1** VR modification package.

**Installation:**

1. Download the **3-in-1** archive from this repository's **Releases** section.
2. Extract the archive.
3. Run the included installer.
4. Select the game or games for which you want to install the VR modification.
5. Follow the installer's instructions.
6. Launch each game using its dedicated launcher.

VR opens in a 1280×960 window by default. You can change this in the launcher settings. Tutorial cards are enabled for new profiles.
<!-- readme-review: VR-FIRST-RUN-DEFAULTS-449 -->

New profiles use **Auto Pickup** by default.
<!-- readme-review: VR-AUTOPICKUP-DEFAULT-456 -->

**Original game executables are not included** in this modification. To uninstall the mod, run the uninstaller in the game folder. It preserves game saves and third-party plugins. Information on backups and restoration is available in the user guides included in the package.

## Important Compatibility Notes

- The installer supports compatible Steam and GOG versions, but behavior may vary depending on the exact build and the condition of the installed game files.
- For **Extraction Point** and **Perseus Mandate**, the launchers can automatically prepare the executables for a larger address space (**Large Address Aware, LAA**) when starting in VR, with backups created before modifying files.
- **Original F.E.A.R. on Steam:** setting the LAA flag on the tested Steam executable causes a launch error. The Steam executable for the original game is therefore **not modified automatically**. VR support is still available, but the game's usable address space may be limited. The installer displays a notice explaining this difference.
- The tested **GOG version of the original F.E.A.R.** already has the LAA flag set in its stock executable.

If the game fails to launch, include the exact game version and store (Steam or GOG) when reporting the problem.

## Languages

The VR interface is available in:

- **English**
- **Russian**

The language is selected during initial VR setup and can also be changed later in the VR interface settings.

**Note:** This refers to the VR interface, its menus, and prompts. Dialogue and other original game content depend on your installed game version and any separately installed localizations.

## Development Status

The main VR ports have been prepared and tested in a headset. **Perseus Mandate has been completed from beginning to end in VR.** The original F.E.A.R. and Extraction Point have also been confirmed playable, although a separate, fully documented completion of each game with the latest build is not claimed.

The project may receive bug fixes, compatibility improvements, and new features. Updates will be released when needed and when the author has time; there is no fixed release schedule.

## Project Background and Attribution

This project was originally based on **F.E.A.R. VR 1.3.1 by TheFreeMike**. That version was reverse engineered to develop ports for the expansions, followed by extensive independent development, compatibility fixes, additional VR interactions, and new systems.

**TheFreeMike has explicitly granted permission to publish this independent version, including the VR modification for the original F.E.A.R. and both expansions.**

**Important disclaimer:**

This is an independent, **unofficial** project by **NeuroLoc**. **TheFreeMike is not involved in developing or maintaining this version, does not endorse it, and does not provide technical support for it.** This project is separate from his own F.E.A.R. VR releases and should not be confused with them.

**Do not contact TheFreeMike about bugs, compatibility issues, or technical support for this project.** Direct all questions about this version to **NeuroLoc**.

This modification is also not an official product of, or endorsed by, the developers or publishers of the original F.E.A.R. games.

## Bug Reports and Technical Support

If you encounter a problem, please open an **Issue** in this GitHub repository. If possible, include:

- The affected game.
- Game version and store (Steam or GOG).
- VR headset model and OpenXR runtime.
- A description of the issue and steps to reproduce it.
- Relevant logs, if available.

Please check existing Issues before submitting a new report.

## Author and Links

The **Information** window in each launcher lists the support contact and NeuroLoc's links.

<!-- readme-review: LAUNCHER-INFORMATION-445 -->
<!-- readme-review: UNINSTALL-CLEANUP-446 -->

**NeuroLoc**

- **GitHub:** https://github.com/NeuroLoc
- **YouTube:** https://www.youtube.com/@NeiroZvukInGame
- **Telegram:** https://t.me/NeiroZvukInGame
- **Boosty:** https://boosty.to/neuroloc

## Distribution and Optional Support

This modification is distributed **free of charge**. Supporting the author through Boosty is entirely optional and is not required to download or use the mod.

Thank you for your interest in the project and for supporting community VR modding!
