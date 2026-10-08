# Cheat Engine Tables for Euro Truck Simulator 2, Red Alert 2 & More

**English** | [简体中文](README.zh-CN.md)

A collection of Cheat Engine cheat tables (`.CT` files) for inspecting and editing game memory on Windows. This repository includes tables for **Euro Truck Simulator 2**, **Command & Conquer: Red Alert 2**, **Yuri's Revenge**, and a table apparently intended for **Plants vs. Zombies**.

The files contain memory addresses and pointer chains. They are editable Cheat Engine tables, with no bundled trainer executable, Lua script, or Auto Assembler script.

## Available cheat tables

| Game | Table | Entries | Target process |
| --- | --- | --- | --- |
| Euro Truck Simulator 2 (ETS2) | [eurotrucks2.CT](eurotrucks2.CT) | Money, experience (XP) | `eurotrucks2.exe` |
| Command & Conquer: Red Alert 2 (RA2) | [red2.CT](red2.CT) | Power, money, power load | `game.exe` |
| Command & Conquer: Red Alert 2 — Yuri's Revenge | [red2_yuir.CT](red2_yuir.CT) | Money | `gamemd.exe` |
| Plants vs. Zombies (apparent target; unverified) | [zhiwu.CT](zhiwu.CT) | Two unnamed entries; their purpose is undocumented | `popcapgame1.exe` |

The table filenames are preserved as stored in the repository, including `red2_yuir.CT`. Entry descriptions inside the tables are currently in Chinese. All entries use the **4 Bytes** value type.

## Quick start

1. Install [Cheat Engine](https://www.cheatengine.org/) on Windows.
2. Download this repository using **Code → Download ZIP** on [GitHub](https://github.com/Fullsize/ce_scripts), or clone it:

   ```sh
   git clone https://github.com/Fullsize/ce_scripts.git
   ```

3. Start the game and load a save or begin a session so its game data is initialized.
4. Open the matching `.CT` file in Cheat Engine using **File → Load**, or double-click the file if `.CT` files are associated with Cheat Engine.
5. Use Cheat Engine's process selector to attach to the process listed in the table above.
6. Check that the displayed value matches the value in the game. Double-click the **Value** field to edit it. For entries that resolve correctly, the checkbox can freeze the value.

Back up your save before editing values. Identify the two unnamed entries in `zhiwu.CT` before changing them.

## Compatibility

These tables use fixed module-relative addresses and pointer offsets. A different game build, executable, or mod can change the memory layout and make an entry stop working.

- **Game versions:** exact supported builds have not been recorded, and compatibility has not been verified across versions.
- **Cheat Engine:** the XML files declare `CheatEngineTableVersion="45"`. This is a table format identifier, not a documented minimum application version.
- **Platform:** the tables reference Windows `.exe` processes. Compatibility with other platforms or compatibility layers has not been verified.
- **Plants vs. Zombies:** the filename and process suggest this game, but the table does not document the game edition or what its two entries modify.

## Troubleshooting

| Symptom | What to check |
| --- | --- |
| A value displays `??` | Attach to the correct process and load into the game. If the value still does not resolve, the pointer chain may not match your build. |
| A number does not match the game | Check the executable and game version. Confirm what the entry represents before editing it. |
| A table stops working after an update | The base address or offsets may need to be located again for the new build. |
| Yuri's Revenge entries do not resolve | Attach to `gamemd.exe`; the Red Alert 2 table targets `game.exe`. |

## Repository layout

```text
ce_scripts/
├── README.md          # English documentation
├── README.zh-CN.md    # Simplified Chinese documentation
├── eurotrucks2.CT     # ETS2 money and experience
├── red2.CT            # Red Alert 2 power, money, and power load
├── red2_yuir.CT       # Yuri's Revenge money
└── zhiwu.CT           # Two unnamed entries targeting popcapgame1.exe
```

## Contributing

Corrections, updated pointer chains, and documented game versions are welcome through [issues](https://github.com/Fullsize/ce_scripts/issues) or pull requests.

For a compatibility report, include the table filename, game version, executable name, Cheat Engine version, and the affected entry. For a table update, describe what each entry controls and which game build you tested. Keep the English and Chinese documentation consistent when changing documented features.
