# Ergo

Ergo is a web browser for Windows. It is built on Ergium, a browser engine
written from scratch: the pages, the browser's own window and its built-in
pages are all drawn by that engine, with no other engine or web view inside.
This repository holds Ergo's releases; it has no source code.

**Ergo is an early preview.** Many pages will look wrong or not work yet,
and much of what browsers usually have is still missing (no sync, no
extensions). Use it to try it out, not as your only browser.

## Install

1. Open the [latest release](https://github.com/ShivankXD/ergo-releases/releases/latest)
   and download `Ergo-Setup-x64.exe`.
2. Run it. Ergo installs for your Windows user only, in
   `%LOCALAPPDATA%\Programs\Ergo`, without asking for administrator rights,
   and adds itself to the Start menu.

Needs Windows 10 or later, 64-bit. Setup is not signed with a code-signing
certificate yet, so Windows SmartScreen may warn before it runs; the
release page lists the SHA-256 of each Setup.

To remove Ergo: Settings > Apps > Installed apps > Ergo > Uninstall. It
asks whether to also remove your Ergo data (history, bookmarks, settings).

## Updates

Ergo updates itself, the way most browsers do: you install it once and do
not run Setup again.

- At start and then every six hours, Ergo asks this repository for the
  latest release's `update.json`. The request is the same from every copy of
  Ergo: it carries no identifier and no version, and nothing about you.
- `update.json` is signed (ECDSA P-256), and Ergo checks the signature with
  a key built into it before it reads anything. It takes only a version
  newer than the one it runs, downloads the update from this repository's
  releases, and uses it only if its size and SHA-256 are the signed ones.
- The new version is unpacked beside the running one. When it is ready, a
  quiet "Updated - Restart" button appears in the bar; Ergo also switches to
  it by itself the next time it starts. If a new version fails to start
  twice, Ergo goes back to the one before.

To turn automatic updates off: the menu > About Ergo > "Install updates
automatically: Turn off". "Check now" is on the same page.

## Privacy

Ergo sends no telemetry: no usage statistics, no crash reports, no
identifiers. The update check above is the only request Ergo makes on its
own. Everything else it fetches is what you ask it to open.

## Licences of bundled software

Ergo bundles no third-party software at present. When it bundles anything
(for example a font), its licence text is added to this repository.
