# Privacy — Cave Command Edge

**Short version: nothing leaves your PC. There is no account, no telemetry, and no
analytics. Neither the widget nor the bridge makes a single outbound internet request.**

## What the widget stores

The widget keeps a small amount of state in the browser storage that iCUE provides for
it, under the `cave-command-edge` namespace:

| Key | Contents |
| --- | --- |
| `stopwatch` | Whether work is running, the start timestamp, accumulated time, and your goal |
| `break-timer` | Break start timestamp, duration, and completed break count |
| `work-session-history` | Completed sessions: timestamp, duration, goal, break count |
| `audio-device-cache` | The names of the last two playback devices seen, so the panel can still label them while the bridge is offline |

This data stays on your machine. It is never transmitted. Deleting the widget from
iCUE, or clearing the session history in the widget, removes it.

## What the widget reads

Track and artist come from the official iCUE Media Data Provider plugin. The widget
reads what iCUE hands it and does not store it.

## What the bridge does

The Cave Command Edge Bridge is an optional Windows companion. It:

- listens on `http://127.0.0.1:47139`, the loopback address only, so it is not
  reachable from your network or the internet;
- enumerates Windows playback devices and reports their names, so the widget can
  label and switch them;
- reports the current media session's source and playback state;
- changes the default playback device, mute state, and master volume when you tap.

It stores no history, writes no logs of your activity, and has no update checker.

## Third parties

There are none. No SDKs, no crash reporting, no ad or analytics networks.

## Your rights

Because no personal data is collected or transmitted, there is nothing for Tom's Cave
to disclose, export, or erase on request. Everything the Software knows about you is
already on your own disk and under your control.

## Contact

Questions: https://github.com/Caveproduction-bot/cave-command-edge/issues
