<p align="center">
  <img src="screenshots/icon.png" width="120" alt="sAiity">
</p>

<h1 align="center">sAiity</h1>

<p align="center">Live subtitles for whatever your Mac is playing.</p>

<p align="center"><a href="https://github.com/enrzh/sAiity/releases/tag/v2.2.0">Download sAiity 2.2</a> · <a href="https://enrzh.github.io/sAiity/privacy.html">Privacy</a> · <a href="https://aiity.de">Part of the aiity family</a></p>

<hr>

<p align="center">
  <img src="screenshots/01-bubble.png" width="92%" alt="sAiity caption bubble with translation">
</p>

<p align="center">
  <img src="screenshots/02-subtitles.png" width="24%" alt="Caption settings">
  <img src="screenshots/03-models.png" width="24%" alt="Local speech and translation models">
  <img src="screenshots/04-library.png" width="24%" alt="Saved transcript library">
  <img src="screenshots/05-dictation.png" width="24%" alt="Press-to-talk dictation settings">
</p>

## What it is

sAiity listens to the audio your Mac is playing, recognises speech on-device,
and shows a stable caption bubble above the screen. Translation can appear as a
second line. Saved sessions keep the original and translated text together.

## What it does

**Captions stay local.** Screen audio is recognised on the Mac. There is no
account, no API key, and no audio upload.

**Translation stays local.** Choose the broad-coverage MADLAD engine, the
Hy-MT2 translation specialist, or a supported local GGUF model.

**Transcripts stay useful.** Save sessions only when you choose to. Read them
inside the app and export bilingual SRT, WebVTT, Markdown, or plain text.

**Dictation is press-to-talk.** Hold the configured key, speak, and release.
The app shows when it is ready, then inserts the result into the focused text
field when possible and always keeps a copy on the clipboard. Dictation
translation has its own opt-in switch and target language, separate from
caption translation.

## Requirements

macOS 26 or later on Apple Silicon. Screen Recording permission is required for
system-audio captions. Accessibility permission is only needed to insert
dictation into another app; clipboard fallback works without it.

## Privacy

Recognition, translation, dictation, and saved transcripts run on-device. The
microphone is opened for captions only when its explicit setting is enabled,
and for dictation only while the press-to-talk key is held. Models are downloaded
from their declared sources; update checks are opt-in.

Read the full [privacy policy](https://enrzh.github.io/sAiity/privacy.html).

## Status

sAiity 2.2 is released for macOS 26 and Apple Silicon. Windows is not a
supported release target.

## Source

This repository is the public product presentation. The implementation source
is kept in a private repository. No source code or reuse license is provided
here.

---

<p align="center"><sub>Built as part of the <a href="https://aiity.de">aiity</a> family.</sub></p>
