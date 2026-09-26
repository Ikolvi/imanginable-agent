# Imanginable agent

The small program that runs the video work for [Imanginable](https://app.imanginable.com)
on **your own computer** — cutting, combining, subtitles, music, export, YouTube upload —
so your video files never leave your machine. It only does what your studio session tells
it to; on its own it does nothing.

This repository holds **releases only**. There is no source here.

## Install

**Windows** (PowerShell):

```powershell
irm https://dl.imanginable.com/install.ps1 | iex
```

Windows will show a *"Windows protected your PC"* SmartScreen notice the first time
(the build is not yet code-signed): click **More info → Run anyway**.

**macOS / Linux**:

```sh
curl -fsSL https://dl.imanginable.com/install.sh | sh
```

Or download the file for your platform from the
[latest release](https://github.com/Ikolvi/imanginable-agent/releases/latest) and run it
from a terminal.

The files are served from `dl.imanginable.com` (Cloudflare, cached worldwide) — the same
files as the GitHub release, which the installers fall back to if that address is down.

## Pair it with your studio

```
imanginable pair --brain https://app.imanginable.com --name my-pc
```

Your browser opens the approval page; click **Approve**. Then `imanginable run`, or
`imanginable service install` to have it start at login.

## Verify a download

`manifest.json` lists every file's SHA-256 and is signed (`manifest.json.minisig`,
minisign format) with the release key whose public half is:

```
RWTsZNgSY0fNrtnzWSv4Fr2UJORVrFtC1HEw31NGO6+acliTcP/w3HVq
```

The agent checks this signature itself before installing any update.

## ffmpeg

The agent does not embed ffmpeg. On first run it downloads a pinned, checksummed
static build (GPL-licensed, with its licence text alongside) into its own data
directory, or uses the one already on your PATH.

Privacy policy: <https://app.imanginable.com/privacy> · Terms: <https://app.imanginable.com/terms>

## DaVinci Resolve and Premiere Pro

The same releases page also carries **Imanginable for DaVinci Resolve and Premiere Pro**
(tags `editor-v*`): a panel inside the editor that opens your Imanginable films and
storyboards as timelines and brings your cut back. Install:

```powershell
irm https://dl.imanginable.com/editor/editor.ps1 | iex
```

```sh
curl -fsSL https://dl.imanginable.com/editor/editor.sh | sh
```

Details: https://editor.imanginable.com/install/
