# ARNF NetCoop - Online Co-op for *A Robot Named Fight*

Two-player online co-op for **A Robot Named Fight**. One player hosts a run, the other
joins, and you fight through the same procedurally-generated run together. Shared rooms,
synced enemies and bosses, shared items/upgrades, A player revive system based on the local multiplayer drone, and resume-your-run-later
support.

**Version 1.0.9** · BepInEx plugin · 2 players

## Download

Grab the latest **`ARNFNetCoop-1.0.9.zip`** from the
[**Releases**](../../releases/latest) page.

The mod checks for updates at startup and shows a notice in the F9 panel when a newer
version is available, so you will know when to come back here for the latest build.

---

## Requirements

- **A Robot Named Fight**
- **BepInEx 5.4.23.2 (x64)** - the mod loader.
- **Both players must run the exact same `ARNFNetCoop.dll` build.** The connection key
  bakes in the mod version, so mismatched builds simply won't connect (you'll see a
  "version mismatch" message rather than a desync).

## Install

Do this on **both** PCs:

1. **Install BepInEx**:
   - Download **BepInEx 5.4.23.2, `win-x64`** from
     <https://github.com/BepInEx/BepInEx/releases>.
     
     • [Direct Link to Windows x64 bit](https://github.com/BepInEx/BepInEx/releases/download/v5.4.23.2/BepInEx_win_x64_5.4.23.2.zip)
   - Extract the zip into your game folder - the one containing `ARobotNamedFight.exe`:
     `…\Steam\steamapps\common\A Robot Named Fight\`
   - Launch the game once, then quit. This generates the `BepInEx\plugins` folder.
2. **Install the mod:**
   - Drop **`ARNFNetCoop.dll`** (from the release zip) into
     `…\A Robot Named Fight\BepInEx\plugins\`.
3. Launch the game.

## How to play

After selecting your save slot in-game, press **F9** to open the NetCoop panel. Pick a connection method:

No port forwarding required with the Steam connection method. If you have Steam running, your Steam name is shown to your partner on any connection method, including Direct/IP (on the partner panel and in pickup messages). A player without Steam simply shows as P1/P2.

### Steam (no setup needed, older Steam API for this game so may be a bit unreliable but local testing was good)
If you're both on Steam, the panel shows a **Steam / Direct IP** toggle.
- **Host:** select **Steam**, click **Host via Steam**, then invite your friend from the
  Steam overlay (**Shift+Tab > Invite**) or have them "Join Game" from their friends list.
- **Join:** accept the invite or right click and join via the friends list.

### Direct / IP (LAN or port-forwarding needed)
- **Host:** select **Direct IP**, click **Host** (default UDP port **24816**).
- **Join:** enter the host's IP and port, click **Join**.

- Keyboard shortcuts: **F10** hosts, **F11** joins, using the panel's current fields.

Once connected, the host starts (or continues) a run and the client drops in. A client can also drop into a host's game midrun if they'd like, they will be synced to the host.

## Top features

- **Host-authoritative.** The first player in "owns" a room and simulates its enemies and
  streams them to the partner. So combat, bosses, hazards, drops, and revives stay in sync.
  Bosses are always "owned" by the host. 
- **Downed-player revives.** When a player dies they become a drone tethered to the
  survivor; grab health pickups or a max hp upgrade, or clear the boss to revive.
- **Resume later.** You may quit and reconnect to the same run. You keep your own loadout,
  upgrades, and position while the world stays in sync with the host. If the host or client advances
  the run solo, you will be forced to re-sync to their progress on the next join.
- **Safe saves** Single-player save *format* is untouched; co-op resume data
  rides in a small side-car file per slot.
- **No game assets are redistributed.** The mod patches your own installed copy of the game
  at runtime. It does not modify any game files on disk.

## Troubleshooting

- **Can't connect / "version mismatch":** make sure both PCs run the *exact same*
  `ARNFNetCoop.dll`. For Direct over the internet, confirm **UDP 24816** is forwarded to the
  host.
- **Mod didn't load:** open `…\A Robot Named Fight\BepInEx\LogOutput.log` and look for
  `ARNF NetCoop v1.0.9 loaded; patches applied: N ok, 0 failed.` If that line is missing,
  BepInEx isn't installed correctly (re-check step 1).

## License & credits

The mod code is released under the [MIT License](LICENSE). Bundled/third-party components
(LiteNetLib, BepInEx, HarmonyX) retain their own licenses. See [CREDITS.txt](CREDITS.txt).
Unofficial fan-made mod; not affiliated with the game's developer or publisher. You must
own the game to use it.
