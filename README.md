<h1 align="center">sAiity</h1>




<p align="center"><strong>Speech on the machine, not in the cloud.</strong></p>




<p align="center">Live captions, translation, transcripts, and press-to-talk dictation for macOS.</p>




<p align="center">
  <a href="https://github.com/enrzh/sAiity/releases/tag/v2.4.1">Release notes v2.4.1</a>
  &nbsp;&middot;&nbsp;
  <a href="https://github.com/enrzh/sAiity/releases/download/v2.4.1/sAiity-2.4.2.dmg">Download DMG</a>
  &nbsp;&middot;&nbsp;
  <a href="https://github.com/enrzh/sAiity/releases/download/v2.4.1/sAiity-2.4.2.zip">Download ZIP</a>
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
| **Dictation** | Hold a configurable key, speak, and release. Local cleanup removes clear fillers and repetitions while preserving the spoken language; waveform feedback keeps the active dictation state visible; the result is inserted into the focused field when possible and also kept on the clipboard. |
| **Transcripts** | Save sessions in the app with original and translated text together. Read them later, scroll through longer subtitle history, or export SRT, WebVTT, Markdown, or plain text. |




## If something needs the network




Daily use does not. sAiity downloads the models you choose from their declared sources, then recognises and translates on-device. The signed app can check the opt-in Sparkle feed for updates. No account or API key is required.

## What's new in 2.4.1

- Faster dictation cleanup by skipping deterministic edits and keeping the selected local cleanup model warm for repeated dictations.
- Safer cleanup and translation for mixed-language dictation, preserving per-region language metadata and never using the first detected language as the whole source.
- Sequential ASR region processing with cancellation-safe native model lifetime handling.
- Nemotron 2240 remains the recommended dictation engine after local latency and code-switching checks; Whisper base remains available as an explicit alternative.
