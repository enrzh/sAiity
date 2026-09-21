# sAiity

<p align="center"><strong>Speech on the machine, not in the cloud.</strong></p>

<p align="center">Live captions, translation, transcripts, and press-to-talk dictation for macOS.</p>

<p align="center">
  <a href="https://github.com/enrzh/sAiity/releases/tag/v2.5.0">Release notes v2.5.0</a>
  &nbsp;&middot;&nbsp;
  <a href="https://github.com/enrzh/sAiity/releases/download/v2.5.0/sAiity-2.5.0.dmg">Download DMG</a>
  &nbsp;&middot;&nbsp;
  <a href="https://github.com/enrzh/sAiity/releases/download/v2.5.0/sAiity-2.5.0.zip">Download ZIP</a>
  &nbsp;&middot;&nbsp;
  <a href="https://enrzh.github.io/sAiity/appcast.xml">Sparkle update feed</a>
  &nbsp;&middot;&nbsp;
  <a href="https://enrzh.github.io/sAiity/privacy.html">Privacy</a>
  &nbsp;&middot;&nbsp;
  <a href="https://aiity.de">aiity</a>
</p>

<hr>

## The product

| Capability | Description |
| --- | --- |
| **Captions** | Speech from your Mac's system audio becomes stable captions in a small, movable bubble. Recognition runs on the Mac. |
| **Translation** | Add a second line in another language with a local translation model. Original speech remains available. |
| **Dictation** | Hold a configurable key, speak, and release. Silence-aware regions preserve natural language switches, while local cleanup removes clear fillers and repetitions; waveform feedback keeps the active dictation state visible; the result is inserted into the focused field when possible and also kept on the clipboard. |
| **Transcripts** | Save sessions in the app with original and translated text together. Read them later, scroll through longer subtitle history, or export SRT, WebVTT, Markdown, or plain text. |

## What's new in 2.5.0

- Code-switching dictation can preserve German, English, Chinese, and other
  spoken spans in one press-to-talk session.
- Whisper and Nemotron reuse resident model weights while decoding regions
  sequentially, reducing warm release-to-result latency.
- Cleanup and translation validate mixed-language output instead of silently
  normalising it to the first detected language.
- Cancellation, model readiness, and release timing are surfaced more clearly
  for a more predictable local workflow.

## If something needs the network

Daily use does not. sAiity downloads the models you choose from their declared sources, then recognises and translates on-device. The signed app can check the opt-in Sparkle feed for updates. No account or API key is required.
