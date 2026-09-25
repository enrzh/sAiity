# sAiity

<p align="center"><strong>Speech on the machine, not in the cloud.</strong></p>

<p align="center">Live captions, translation, transcripts, and press-to-talk dictation for macOS.</p>

<p align="center">
  <a href="https://github.com/enrzh/sAiity/releases/tag/v2.5.5">Release notes v2.5.5</a>
  &nbsp;&middot;&nbsp;
  <a href="https://github.com/enrzh/sAiity/releases/download/v2.5.5/sAiity-2.5.5.dmg">Download DMG</a>
  &nbsp;&middot;&nbsp;
  <a href="https://github.com/enrzh/sAiity/releases/download/v2.5.5/sAiity-2.5.5.zip">Download ZIP</a>
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

## What's new in 2.5.5

- Reorganized caption, dictation, model, and transcript settings into clearer task-focused pages.
- Improved model readiness and download-state reporting, with safer model inventory refresh and interrupted-download cleanup.
- Added local caption timing diagnostics and protected vocabulary for names and technical terms.
- Continued caption reliability work with bounded ASR processing, adaptive overload handling, language-aware merging, and stable bubble updates.
- Verified 410 tests across 53 suites. The signed ZIP and styled drag-to-Applications DMG are notarized and stapled.

DMG SHA-256: 80c13d4ff55e1f37243376a9ec3fee3eba387aff412ca8303d02f8e41060f2d5

ZIP SHA-256: e6909ef78f49464852d6c3a6b79d0d24bdf2225fbb9e49fd3573f1e49ba19b53

## What's new in 2.5.3

- Adaptive speech activity detection closes live captions at natural pauses and
  distinguishes healthy silence from a stalled capture stream.
- Stable cumulative ASR reconciliation reduces duplicated or missing words
  around pauses and recognizer revisions.
- Bounded ASR processing, sample-clock timestamps, backlog diagnostics, and
  generation-safe translation keep captions responsive during long sessions.
- Script-aware joining preserves readable Latin spacing and spaceless scripts.

## What's new in 2.5.0

- Code-switching dictation can preserve German, English, Chinese, and other
  spoken spans in one press-to-talk session.
- Whisper and Nemotron reuse resident model weights while decoding regions
  sequentially, reducing warm release-to-result latency.
- Cleanup and translation validate mixed-language output instead of silently
  normalising it to the first detected language.
- Cancellation, model readiness, and release timing are surfaced more clearly
  for a more predictable local workflow.

## What's new in 2.5.1

- Removed the duplicate top-right Advanced settings action from Dictation and Captions.
- Polished the remaining native disclosure with a slider icon, compact semibold typography, improved spacing, and localized labels.
- Verified 374 tests in 48 suites, plus Developer ID signing, Apple notarization, and the styled drag-to-Applications DMG.

## What's new in 2.5.2

- Clearing the caption bubble now starts a fresh visible display row while the
  recognition session continues, so new speech appears without restarting
  captions and late translations cannot repaint the cleared row.
- Captions show their listening state before translator warm-up completes and
  choose between already-installed ASR tiers using caption-specific latency
  measurements; dictation keeps its own adaptive history.
- Verified 380 tests in 49 suites, Apple notarization, and the styled
  drag-to-Applications DMG.

## If something needs the network

Daily use does not. sAiity downloads the models you choose from their declared sources, then recognises and translates on-device. The signed app can check the opt-in Sparkle feed for updates. No account or API key is required.
# sAiity

<p align="center"><strong>Speech on the machine, not in the cloud.</strong></p>

<p align="center">Live captions, translation, transcripts, and press-to-talk dictation for macOS.</p>

<p align="center">
  <a href="https://github.com/enrzh/sAiity/releases/tag/v2.5.3">Release notes v2.5.3</a>
  &nbsp;&middot;&nbsp;
  <a href="https://github.com/enrzh/sAiity/releases/download/v2.5.3/sAiity-2.5.3.dmg">Download DMG</a>
  &nbsp;&middot;&nbsp;
  <a href="https://github.com/enrzh/sAiity/releases/download/v2.5.3/sAiity-2.5.3.zip">Download ZIP</a>
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

## What's new in 2.5.3

- Adaptive speech activity detection closes live captions at natural pauses and
  distinguishes healthy silence from a stalled capture stream.
- Stable cumulative ASR reconciliation reduces duplicated or missing words
  around pauses and recognizer revisions.
- Bounded ASR processing, sample-clock timestamps, backlog diagnostics, and
  generation-safe translation keep captions responsive during long sessions.
- Script-aware joining preserves readable Latin spacing and spaceless scripts.

## What's new in 2.5.0

- Code-switching dictation can preserve German, English, Chinese, and other
  spoken spans in one press-to-talk session.
- Whisper and Nemotron reuse resident model weights while decoding regions
  sequentially, reducing warm release-to-result latency.
- Cleanup and translation validate mixed-language output instead of silently
  normalising it to the first detected language.
- Cancellation, model readiness, and release timing are surfaced more clearly
  for a more predictable local workflow.

## What's new in 2.5.1

- Removed the duplicate top-right Advanced settings action from Dictation and Captions.
- Polished the remaining native disclosure with a slider icon, compact semibold typography, improved spacing, and localized labels.
- Verified 374 tests in 48 suites, plus Developer ID signing, Apple notarization, and the styled drag-to-Applications DMG.

## What's new in 2.5.2

- Clearing the caption bubble now starts a fresh visible display row while the
  recognition session continues, so new speech appears without restarting
  captions and late translations cannot repaint the cleared row.
- Captions show their listening state before translator warm-up completes and
  choose between already-installed ASR tiers using caption-specific latency
  measurements; dictation keeps its own adaptive history.
- Verified 380 tests in 49 suites, Apple notarization, and the styled
  drag-to-Applications DMG.

DMG SHA-256: `b4725e508caa0307d79c938af063ca955307ee2384f78a5ed05539499f6c9141`

ZIP SHA-256: `5752171bb5bdd82c1b52356b114e73a0914edd96f401b595e05bcce70081988f`

## If something needs the network

Daily use does not. sAiity downloads the models you choose from their declared sources, then recognises and translates on-device. The signed app can check the opt-in Sparkle feed for updates. No account or API key is required.
