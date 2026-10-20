<p align="center"><img src="screenshots/icon.png" width="100" alt="Syllivra app icon"></p>

<h1 align="center">Syllivra</h1>
<p align="center"><strong>Read what you hear. Keep what matters.</strong><br>Live captions, translation, dictation and transcripts. On your Mac.</p>
<p align="center">
  <a href="https://github.com/enrzh/sAiity/releases/download/v2.7.0/Syllivra-2.7.0.dmg">Download for Mac</a> ·
  <a href="https://enrzh.github.io/sAiity/">Explore the app</a> ·
  <a href="https://github.com/enrzh/sAiity/releases/tag/v2.7.0">Release notes</a> ·
  <a href="https://enrzh.github.io/sAiity/en/privacy.html">Privacy</a>
</p>

<p align="center"><img src="screenshots/captions.png" width="860" alt="Fresh capture of the native Captions window, with speech model, update speed, translation and caption bubble controls"></p>
<p align="center"><img src="screenshots/bubble.png" width="620" alt="A caption bubble with English example text and its German translation"></p>

**macOS 26 or later · Apple Silicon · No account or API key.**

## From listening to doing

- **Follow the conversation.** System audio becomes captions in a movable
  bubble. Nemotron offers Realtime or Balanced subtitle timing; Qwen is an
  optional pause-based alternative.
- **Keep both languages.** Local translation sits below the original. Choose
  complete sentences or realtime previews as the sentence grows.
- **Speak. Release. Done.** Hold your dictation shortcut, speak and release.
  The result is inserted into the field you started in when possible, and stays
  on the clipboard. Captions and dictation have independent model and language
  choices. A local dictionary protects names and stores explicit corrections.
- **Take the words with you.** Save bilingual transcripts, search sessions,
  and export SRT, WebVTT, Markdown or plain text. Add a local summary to revisit
  the essentials without changing the original spoken lines.

<p align="center">
  <img src="screenshots/dictation.png" width="420" alt="Dictation settings with the hold-to-talk shortcut, processing mode, translation and cleanup choices">
  <img src="screenshots/summary.png" width="420" alt="An example transcript with a local recap, decisions and action items">
</p>

Freshly captured on **October 20, 2026**, from the **2.7.0 release UI** using
synthetic caption and transcript text. See [image provenance](screenshots/README.md).

## Install

1. [Download the signed, notarized DMG](https://github.com/enrzh/sAiity/releases/download/v2.7.0/Syllivra-2.7.0.dmg)
   and move Syllivra to Applications. [A ZIP is also available](https://github.com/enrzh/sAiity/releases/download/v2.7.0/Syllivra-2.7.0.zip).
2. Choose captions, dictation or both. Setup walks you through local model
   downloads and the permissions for your chosen features.
3. For captions, macOS Screen Recording permission gates system audio. Dictation
   uses the microphone; Accessibility permits insertion into another app.

Models are downloaded on first use, not bundled in the app. Speed and storage
requirements depend on the models and your Mac. Intel Macs and Windows are not
supported releases.

## Privacy

Audio, recognition, translation and transcripts stay on your Mac. No audio
uploads, account, analytics or API key. Internet access is needed for model
downloads and optional update checks.

The caption microphone mixer is off by default. Dictation uses the microphone
only while you hold the shortcut. Sparkle update checks are opt-in.

[English policy](https://enrzh.github.io/sAiity/en/privacy.html) ·
[Datenschutzerklärung](https://enrzh.github.io/sAiity/privacy.html)

## Current release: 2.7.0

Existing installs update in place and keep their settings, downloaded models,
transcripts and `saiity://` links. Installing from the DMG? Quit the older
version, replace its app bundle with Syllivra and keep only one installed copy.

Dictation works straight from the shortcut with redesigned settings and setup,
and now pastes into browser and Electron text fields, including Chrome. It says
when it heard near-silence, skips silent stretches and never opens the
microphone for other modifier shortcuts. New local model options, faster
capture, reused warm models and steadier language handling round it out.

[Release notes and verification](https://github.com/enrzh/sAiity/releases/tag/v2.7.0) ·
[All releases](https://github.com/enrzh/sAiity/releases) ·
[Signed Sparkle feed](https://enrzh.github.io/sAiity/appcast.xml)

| Artifact | SHA-256 |
| --- | --- |
| DMG | `71cbb32a91c055f3db8c419694ed68559bb5c6a30825d9cf582c4da9a0403cad` |
| ZIP | `ae104c82c329c637472d02169b060b2d3da39688f582c0d76d27ec7274020483` |

## About this repository

This repository holds public release assets, the website and privacy policies.
The application source is maintained separately. This is not an open-source
distribution of the app.

GitHub Pages serves plain HTML and CSS from the root of `main`. No framework,
build step, tracking scripts or external fonts. Preview locally with
`python3 -m http.server 8080` and open it using ego-browser. Keep versioned
download links aligned with the published release; publish release assets
before updating the signed feed.

Part of [aiity](https://aiity.de) · [hAiity for iPhone](https://enrzh.github.io/hAiity/)
