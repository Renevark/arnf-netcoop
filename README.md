# ARNF NetCoop — Online Co-op for *A Robot Named Fight*

Two-player online co-op for **A Robot Named Fight**. One player hosts a run, the other
joins, and you fight through the same procedurally-generated run together — shared rooms,
synced enemies and bosses, shared loot, downed-player revives, and resume-your-run-later
support.

**Version 1.0.0** · BepInEx plugin · 2 players

## ⬇️ Download

Grab the latest **`ARNFNetCoop-1.0.0.zip`** from the
[**Releases**](../../releases/latest) page.

---

## Requirements

- **A Robot Named Fight** (Steam).
- **BepInEx 5.4.23.2 (x64)** — the mod loader.
- **Both players must run the exact same `ARNFNetCoop.dll` build.** The connection key
  bakes in the mod version, so mismatched builds simply won't connect (you'll see a
  "version mismatch" message rather than a desync).

## Install

Do this on **both** PCs:

1. **Install BepInEx** (once):
   - Download **BepInEx 5.4.23.2, `win-x64`** from
     <https://github.com/BepInEx/BepInEx/releases>.
   - Extract the zip into your game folder — the one containing `ARobotNamedFight.exe`:
     `…\Steam\steamapps\common\A Robot Named Fight\`
   - Launch the game once, then quit. This generates the `BepInEx\plugins` folder.
2. **Install the mod:**
   - Drop **`ARNFNetCoop.dll`** (from the release zip) into
     `…\A Robot Named Fight\BepInEx\plugins\`.
3. Launch the game. You're modded.

## How to play

In-game, press **F9** to open the NetCoop panel. Pick a connection method:

### Steam (recommended — no setup)
If you're both on Steam, the panel shows a **Steam / Direct IP** toggle.
- **Host:** select **Steam**, click **Host via Steam**, then invite your friend from the
  Steam overlay (**Shift+Tab → Invite**) or have them "Join Game" from their friends list.
- **Join:** accept the invite — there's no IP to type.

No port forwarding required.

### Direct / IP (LAN or port-forwarded)
- **Host:** select **Direct IP**, click **Host** (default UDP port **24816**).
- **Join:** enter the host's IP and port, click **Join**.
  - **Same network (LAN):** use the host's local IP, e.g. `192.168.x.x`.
  - **Over the internet:** use the host's public IP and forward **UDP 24816** to the host PC.
- Keyboard shortcuts: **F10** hosts, **F11** joins, using the panel's current fields.

Once connected, the host starts (or continues) a run and the client drops in. Play together!

## Good to know

- **Host-authoritative.** Whoever "owns" a room simulates its enemies and bosses and
  streams them to the partner, so combat, bosses, hazards, drops, and revives stay in sync.
- **Downed-player revives.** When a player dies they become a revival drone tethered to the
  survivor; grab a max-life-up / full-heal to come back, or clear the boss to revive.
- **Resume later.** Quit and reconnect to the same run — you keep your own loadout,
  upgrades, and position while the world stays in sync with the host. If the host advances
  the run solo while you're away, you re-sync to their progress on the next join.
- **Your saves are safe.** Single-player save *format* is untouched; co-op resume data
  rides in a small side-car file per slot.
- **No game assets are redistributed.** The mod patches your own installed copy of the game
  at runtime — it does not modify any game files on disk.

## Troubleshooting

- **Can't connect / "version mismatch":** make sure both PCs run the *exact same*
  `ARNFNetCoop.dll`. For Direct over the internet, confirm **UDP 24816** is forwarded to the
  host.
- **Mod didn't load:** open `…\A Robot Named Fight\BepInEx\LogOutput.log` and look for
  `ARNF NetCoop v1.0.0 loaded; patches applied: N ok, 0 failed.` If that line is missing,
  BepInEx isn't installed correctly (re-check step 1).

## License & credits

The mod code is released under the [MIT License](LICENSE). Bundled/third-party components
(LiteNetLib, BepInEx, HarmonyX) retain their own licenses — see [CREDITS.txt](CREDITS.txt).
Unofficial fan-made mod; not affiliated with the game's developer or publisher. You must
own the game to use it.
