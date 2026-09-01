# Cave Command Edge

Support, downloads and release notes for **Cave Command Edge** — a touch dashboard
widget for the CORSAIR XENEON EDGE.

**Get the widget:** [Elgato Marketplace](https://marketplace.elgato.com/@tomscave)

This repository is for support and for the free companion bridge. The widget itself is
distributed through Elgato Marketplace.

---

## What it does

One 2560×720 touch dashboard for the XENEON EDGE:

- **Media** — track and artist from the official iCUE Media Data Provider, with
  previous, play/pause and next as full-height touch targets.
- **Work time** — a stopwatch built from timestamps rather than ticks, so an
  eight-hour day survives restarts, sleep and iCUE reloads. Adjustable goal in
  30-minute steps, with elapsed, remaining and percent complete.
- **Breaks** — a 15-minute break pauses work and resumes on its own, counted per
  session.
- **Sessions** — completed days persist newest-first with duration and break count,
  a running total, and delete behind a confirm step.
- **Clock** — 24-hour time with seconds, day and full date.
- **Audio** — switch between two Windows playback devices, mute, and drag master
  volume. Requires the companion bridge below.

## Requirements

- iCUE **5.47** or later
- Windows
- A XENEON EDGE dashboard LCD

## Installing the widget

1. Buy and download Cave Command Edge from Elgato Marketplace.
2. In iCUE, open the **XENEON EDGE → Widgets** screen.
3. Import `CaveCommandEdge.icuewidget`.

## Installing the companion bridge (optional, free)

The audio panel needs a small Windows companion application. Everything else works
without it.

1. Download the latest `CaveCommandEdgeBridge-Setup.exe` from
   [Releases](../../releases).
2. Run it. Windows SmartScreen may warn that the publisher is unrecognised — the
   installer is not code-signed yet. Choose **More info → Run anyway** if you are
   happy to proceed.
3. The bridge starts automatically and listens on `127.0.0.1:47139`. Nothing is
   exposed to your network or the internet.

The widget picks it up within a second or two, and the audio panel stops reporting
"Audio bridge offline".

## Troubleshooting

**The widget does not appear in iCUE.**
Check you are on iCUE 5.47 or later. Earlier versions do not support the widget
framework this uses.

**Media shows "Connecting to media…" or "Media unavailable".**
The widget reads whatever the official iCUE Media Data Provider reports. Start
playback in a supported player and give it a moment. If iCUE itself shows no media
session, the widget cannot either.

**The audio panel says "Audio bridge offline".**
The bridge is not running. Check for `CaveCommandEdgeBridge` in Task Manager and
reinstall from Releases if it is missing.

**Only two audio devices are listed.**
That is by design. The panel shows two playback outputs.

**My work timer reset.**
It should not — the timer is stored as timestamps. Please
[open an issue](../../issues) with what happened just before, and whether iCUE was
restarted or updated.

## Known limitations

These are not implemented because the documented iCUE Widget API does not expose them:

- Stop transport, and switching between media sessions or sources
- Album artwork retrieval
- Windows audio device switching beyond two outputs

## Support

[Open an issue](../../issues). Please include your iCUE version, Windows version, and
whether the bridge is installed.

## Privacy

Nothing leaves your PC. No account, no telemetry, no outbound network requests. See
[PRIVACY.md](PRIVACY.md).

## Licence

Commercial. See [LICENSE.md](LICENSE.md).

CORSAIR, iCUE and XENEON are trademarks of their respective owners. Tom's Cave is not
affiliated with or endorsed by Corsair.
