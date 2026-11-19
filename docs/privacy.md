# ThumbFree for Windows privacy policy

*Last updated: 20 November 2026*

ThumbFree is a voice-typing app. **It recognises speech on your PC and never sends your voice or your text to us or
anyone else.** There is no account, no advertising and no analytics. (ThumbFree for Android has
[its own policy](https://github.com/shivam098/thumbfree-android/blob/main/docs/privacy.md), with the same rules.)

## What ThumbFree uses and why

| Data or permission | Used for | Leaves your PC? |
|---|---|---|
| **Microphone** | Hearing you, only from one tap of Ctrl+Win to the next (10 minutes at most). | No. Audio is kept in memory, turned into text on the PC, then discarded. |
| **Text you dictate** | Typing it into the text box you're using, and **History** (below). | No. |
| **The text box you dictate into** | Spacing, capital letters, and email or list layout (below). | No. It isn't stored. |
| **Notifications** | Telling you if the microphone goes silent while you speak, and keeping a dictation that couldn't be typed so you can copy it. | No. |
| **Internet** | Downloading the speech models once, from the addresses listed in the app's source code. Each file is checked against a fixed SHA-256 fingerprint. | Only standard download requests. No personal data is sent. |
| **Settings, word list, personal dictionary** | Your preferences, in `%APPDATA%\ThumbFree\settings.json`. | No. |

## The text box you dictate into

When you start, ThumbFree uses Windows UI Automation to find out what kind of box it is and to read the text before the
cursor. It reads whether the box is a password, search or multi-line box, and whether it's in an email app. It uses
this for spacing, capital letters and email or list layout, and then types into that same box. This information isn't
stored.

- Chrome, Edge and apps built on them describe their text boxes only once their accessibility support is on. When a
  dictation starts in one of them and its text box can't be seen yet, ThumbFree asks the app to turn it on, the way
  screen readers do: it reads what kind of element each part of that window is, and the titles of its pages. These are
  discarded at once.
- Nothing else on your screen is read.
- Password fields are never typed into.

## History (on by default, can be turned off)

ThumbFree keeps the **text** of your dictations from the last 30 days (at most 500), with the app each was for and the
time, so you can copy one again. It's stored in `%LOCALAPPDATA%\ThumbFree\history.txt` on your PC and never sent
anywhere. No audio is kept.

- Nothing is kept from password fields, or from browser windows that say they're private.
- **Clear** deletes it all, and turning **Keep history** off deletes it and stops keeping new dictations.

## "Help improve ThumbFree" (optional, off by default)

If you turn this on, ThumbFree keeps your dictations in `%LOCALAPPDATA%\ThumbFree\samples` so you can choose to share
them. Each one includes the audio, the recognised text, the typed text, the model name and the app version.

- Nothing is kept from password fields, nor from web browsers, because a browser can't reliably say whether a window
  is private.
- Nothing is sent automatically. To share them, you save a zip yourself and send it however you like (for example, by
  email to the ThumbFree developer).
- ThumbFree keeps at most 300 dictations (150 MB). **Delete all** in Settings removes them.
- If you send dictations to the developer, they're used only to measure and improve recognition, aren't shared with
  anyone else, and are deleted on request.

## Logs

`%LOCALAPPDATA%\ThumbFree\logs` holds timings and error names, never your words. Logs older than 7 days are deleted.

## Uninstalling

Exit ThumbFree from the tray, delete its folder, then `%LOCALAPPDATA%\ThumbFree` and `%APPDATA%\ThumbFree`.

## Children

ThumbFree isn't directed at children under 13.

## Changes and contact

Changes to this policy are published at this address, with the date at the top. For questions or deletion requests,
open an issue at <https://github.com/shivam098/thumbfree-windows/issues>.
