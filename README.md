# ThumbFree for Windows

**Type with your voice, not your thumbs. 100% offline.**

Tap **Ctrl+Win**, speak, tap it again: your words are typed into whatever app you're using, cleaned up and punctuated.
Speech is recognised on your PC; nothing you say is uploaded, and there's no account. ThumbFree replaces Voice
Dictation: your settings, personal dictionary and downloaded models carry over the first time it starts.

- **Live typing:** each phrase is typed as soon as you've moved on to the next one, and the words not typed yet show in
  the pill. "Friday at 3 pm… actually 4 pm" or "scratch that" can still fix the phrase you're saying.
- **Writes like you meant to:** filler words ("um", "you know", "thik hai na") and repeats are left out, punctuation
  is added, and spoken punctuation works ("comma", "new line").
- **Emails and lists, laid out for you.**
- **Only where you are:** the text box is checked right before every piece that's typed. If you've moved to another
  window, tab or box, nothing more is typed: the whole dictation waits in a notification, and a click copies it.
  Password fields are never typed into.
- **English and Hindi + English** (Alt+Shift+H), **History** of the last 30 days, the app window and a first-run guide.

## Install

Download `ThumbFree-x.y.z-win-arm64.zip` (Snapdragon and other ARM PCs) or `ThumbFree-x.y.z-win-x64.zip` (Intel and
AMD) from [Releases](https://github.com/shivam098/thumbfree-windows/releases), unzip it and run `ThumbFree.exe`. A short
guide sets up the microphone and the speech model. Exit Voice Dictation and Voice Assistant first: they also use
Ctrl+Win.

Everything else, from the models and the settings file to how to build it, is in [docs/windows.md](docs/windows.md).
Privacy: [docs/privacy.md](docs/privacy.md).

## Build

```powershell
git clone https://github.com/shivam098/thumbfree-windows
cd thumbfree-windows
dotnet test ThumbFree.slnx -c Release
.\scripts\install.ps1      # builds and installs to %LOCALAPPDATA%\Programs\ThumbFree
```

## Other platforms

ThumbFree also runs on [Android](https://github.com/shivam098/thumbfree-android); a
[Mac](https://github.com/shivam098/thumbfree-mac) version is in development and an
[iPhone](https://github.com/shivam098/thumbfree-ios) version is planned. Every app follows the same feature reference:
[PLAN.md, section 3](https://github.com/shivam098/thumbfree-android/blob/main/docs/PLAN.md#3-feature-reference-built-on-android-copy-to-every-platform).

`tests/vectors` (how each test sentence must come out) and `tests/audio` (speech recordings) are the same files in
every ThumbFree repo. The **Test data in sync** check fails while this copy differs from the others: when you change
one, copy the change to all four repos.

## Credits

English: the Kroko streaming model by [Banafo](https://huggingface.co/Banafo/Kroko-ASR) (CC BY-SA 4.0) with the
[Edge-Punct-Casing](https://huggingface.co/frankyoujian/Edge-Punct-Casing) punctuation model (Apache-2.0), and NVIDIA
Parakeet TDT ([110M](https://huggingface.co/nvidia/parakeet-tdt_ctc-110m),
[0.6B v2](https://huggingface.co/nvidia/parakeet-tdt-0.6b-v2); CC BY 4.0), on
[sherpa-onnx](https://github.com/k2-fsa/sherpa-onnx) (Apache-2.0) and ONNX Runtime (MIT). Hindi + English:
[Whisper.net](https://github.com/sandrohanea/whisper.net) (MIT) running quantized conversions of Oriserve's Whisper
Hindi-to-Hinglish models (Apache-2.0), with [Silero VAD](https://github.com/snakers4/silero-vad) (MIT) and
[NAudio](https://github.com/naudio/NAudio) (MIT). Full list: [THIRD-PARTY-NOTICES.md](THIRD-PARTY-NOTICES.md).
