<div align="center">

# DualBracket

**Offline-first tournament bracket & live scoring manager for Mobile Legends: Bang Bang (5v5) and Pickleball.**

<p>
  <a href="https://github.com/nekofied143/Tournament-Create/releases/latest">
    <img src="https://img.shields.io/github/v/release/nekofied143/Tournament-Create?style=for-the-badge&logo=github&label=LATEST%20RELEASE&color=0284C7" alt="Latest Release" />
  </a>
  <a href="https://github.com/nekofied143/Tournament-Create/releases">
    <img src="https://img.shields.io/github/downloads/nekofied143/Tournament-Create/total?style=for-the-badge&logo=github&label=DOWNLOADS&color=2563EB" alt="Downloads" />
  </a>
</p>

<p>
  <img src="https://img.shields.io/badge/Android-7.0%2B-3DDC84?style=flat-square&logo=android&logoColor=white" alt="Android 7.0+" />
  <img src="https://img.shields.io/badge/Design-Material%203-7C3AED?style=flat-square" alt="Design Material 3" />
  <img src="https://img.shields.io/badge/Built%20With-Jetpack%20Compose-0EA5E9?style=flat-square&logo=kotlin&logoColor=white" alt="Jetpack Compose" />
  <img src="https://img.shields.io/badge/Offline-100%25%20Local%20Room%20DB-10B981?style=flat-square" alt="Offline Room DB" />
</p>

<h3>
  <a href="https://github.com/nekofied143/Tournament-Create/releases/latest">⬇️ Download Latest APK</a>
  &nbsp;•&nbsp;
  <a href="./RELEASE_NOTES.md">📋 View Release Notes</a>
</h3>

</div>

---

## Overview

| Spec | Details |
| :--- | :--- |
| **Application ID** | `com.aistudio.dinkbracket.pkbtmz` |
| **Current Version** | [![Latest Release](https://img.shields.io/github/v/release/nekofied143/Tournament-Create?label=Latest&color=0284C7)](https://github.com/nekofied143/Tournament-Create/releases/latest) |
| **Supported Android** | Android 7.0 (`minSdk 24`) – Android 16 (`targetSdk 36`) |
| **Game Modes** | Mobile Legends: Bang Bang (5v5) & Pickleball |
| **Distribution** | [GitHub Releases (`nekofied143/Tournament-Create`)](https://github.com/nekofied143/Tournament-Create/releases) |

---

## Features

### 1. Dual-Mode Tournament Engine
- **Mobile Legends: Bang Bang (5v5)**
  - Team registration with **Team Name**, **Tag**, **Captain**, and **4 Teammates** (full 5-player roster) plus duplicate IGN/conflict checks.
  - Per-match **Blue Side / Red Side** selector, **1st Pick** slot indicator, and **Custom Lobby ID / Password** tracking.
  - Configurable **BO1 / BO3 / BO5 / BO7** series per round and per match.
  - Dedicated tournament lobbies (`Lb 1`, `Lb 2`, ...) with 40-minute default scheduling intervals.
- **Pickleball**
  - Singles and Doubles support with configurable **Points to Win** (e.g., 11, 15, 21), **Win by 2**, and **BO1–BO7** game series.
  - Built-in **Player Shuffler** (`PlayerShufflerDialog`) to randomize checked-in players into paired teams.
  - Automated court assignment (`Ct 1`, `Ct 2`, ...) with 25-minute default scheduling intervals.

### 2. Bracket Formats & Operations
- **Single Elimination**, **Double Elimination** (Upper Bracket, Lower Bracket, Grand Finals), and **Round Robin (Pool Play)**.
- **Grand Finals Twice-to-Beat / Bracket Reset** toggle for Double Elimination tournaments.
- **Per-Round Series Customization** (`RoundSeriesConfigDialog`) to assign BO1, BO3, BO5, or BO7 independently for each round.
- **Bye Assignment Modes:** Top-Seeded Byes or Random Byes.
- **Manual Bracket Overrides** (`ManualOverrideDialog`) to reassign teams, adjust court/lobby numbers and start times, set forced winners, or log override notes with full downstream propagation.
- **One-Tap Sample Tournaments:** Instant MLBB 5v5 Double Elimination and Pickleball 8-team sample brackets.

### 3. Live Scoring, Standings & Exports
- **Live Scoring Sheet** (`LiveScoringSheet`): Score games/sets in real time, save partial progress, or finalize results to advance brackets automatically.
- **Standings & Tiebreakers** (`StandingsTab`): Automatic placement labels (`Champion`, rankings, wins/losses, and point/game differentials).
- **PDF Bracket & Report Export** (`TournamentPdfExporter`): Generates multi-page tournament summary & bracket PDFs via `PdfDocument` for sharing (`FileProvider`) or saving via Storage Access Framework.
- **JSON Backup & Restore** (`TournamentBackupCodec`): Exports and restores complete tournaments, 5v5 rosters, matches, and scores cleanly in portable `.json` files.

### 4. Adaptive Phone, Tablet & Landscape UI
- **Tournament Hub** (`TournamentHubScreen`): Two-pane layout at `>= 700.dp` width with adaptive hero banner and 2-column saved events grid.
- **Workspace Navigation** (`TournamentWorkspaceScreen`): Switches automatically from a bottom `NavigationBar` to a side `NavigationRail` at `>= 600.dp` width with `WindowInsets.safeDrawing` protection.
- **Responsive Grids & Modals**: Two-column grids and side-by-side panes across Teams, Bracket, Matches, Standings, Create Event, Live Scoring, and Round Series dialogs.

### 5. In-App Update Manager (GitHub Releases)
- Checks [`releases/latest`](https://api.github.com/repos/nekofied143/Tournament-Create/releases/latest) automatically on startup and on-demand from the Hub.
- **Formatted Release Notes** (`ReleaseNotesMarkdown`): Renders Markdown headings as version/build pills, hanging-indent bullet & numbered lists, **bold**, *italic*, and monospace `` `code` `` highlights.
- **Zero-Folder Streaming Updates** (`UpdateRepository` + `UpdateInstallReceiver`): Streams updates directly into Android's `PackageInstaller.Session` without saving `.apk` files into `Downloads` or cache directories, and cleans up stale update sessions automatically.
