# Fieldwire Client — Releases

Public distribution point for the **Fieldwire Client** desktop app (Upper Canada Specialty Hardware).

This repository contains **only built release artifacts** — installers and auto-update
metadata. **No source code lives here.** The application source is maintained in a separate
**private** repository; this repo exists solely so the installed app (and new users) can
download releases and receive automatic updates **without** needing access to the private
codebase.

## What's here

Each entry under the **Releases** tab attaches:

- `Fieldwire-Client-Setup-<version>.exe` — the Windows installer (what you download to install the app).
- `latest.yml` + `Fieldwire-Client-Setup-<version>.exe.blockmap` — auto-update metadata the
  installed app reads to detect and download new versions.
- `fieldwire_client.exe` — legacy CLI build, kept for older installs.

## Installing

Download the latest `Fieldwire-Client-Setup-<version>.exe` from the
[latest release](../../releases/latest) and run it. The installer places the app under your
user profile by default — no admin rights required.

## How releases get here

Releases are published **automatically** by CI from the private source repository on every
merge to its `main` branch. **Do not commit, push, or upload to this repo by hand** — the
README scaffold is the only hand-authored content; everything else arrives as release assets.

## Why a separate repo

Distribution is intentionally **decoupled** from source (the standard "CI/CD repo separate
from the live-production repo" pattern). The installed app points at *this* public repo, not
at the private source repo — so the source can be moved, renamed, or kept fully private
without ever breaking auto-update for already-installed apps. Only the finished,
publicly-downloadable installer lands here; the source and the build pipeline stay private.

---

© Upper Canada Specialty Hardware. All rights reserved.
