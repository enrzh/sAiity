# sAiity

<p align="center"><strong>Speech on the machine, not in the cloud.</strong></p>

<p align="center">Live captions, translation, transcripts, and press-to-talk dictation for macOS.</p>

<p align="center">
  <a href="https://github.com/enrzh/sAiity/releases/tag/v2.6.3">Release notes v2.6.3</a>
  &nbsp;&middot;&nbsp;
  <a href="https://github.com/enrzh/sAiity/releases/download/v2.6.3/sAiity-2.6.3.dmg">Download DMG</a>
  &nbsp;&middot;&nbsp;
  <a href="https://github.com/enrzh/sAiity/releases/download/v2.6.3/sAiity-2.6.3.zip">Download ZIP</a>
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

## What's new in 2.6.3

- Automatic insertion requires the press-time app and accessibility field to stay
  focused; otherwise the result is copied.
- Clipboard write failures keep the complete result in a persistent bubble whose
  action is **Retry Copy**; retry copies the retained text without pasting.
- Caption cold/warm timing and release-quality evidence fingerprints are tighter;
  setup restores the persisted automatic-update preference.
- Verified 604 tests across 76 suites; signed ZIP and styled DMG are notarized
  and stapled.

DMG SHA-256: 6186afb35c409af2e476e56bf78e6b6fdbbd9b96e3ca7a9abed29489432bd785

ZIP SHA-256: 5a2d5fd5845b71dd7cb330fe0be3fe4cac791643749436d83475898f2268f8ea

## What's new in 2.6.2

- Failed caption pumps become terminal instead of silent; Qwen keeps a fixed PCM
  bound through silence; cleanup/translation share one generation budget with a
  real deadline.
- Speaker labels ride confirmed audio only; translation output is validated the
  same way on every engine, including mixed-language preservation.
- The release script gates notarization on a clean-source quality matrix.
- Verified 590 tests across 75 suites; signed ZIP and styled DMG are notarized
  and stapled.

DMG SHA-256: c886d4069b004b09fc3ff0ec4df27185ba0c576674ccc0856cad9e84d8a0bc7a

ZIP SHA-256: ca89d4778cc2c735b38ac683704b1ebceb0e852057326bcb7e425388f35dc873

## What's new in 2.6.1

- Qwen3-ASR is a selectable caption engine alongside Nemotron; the language row
  now matches what the active engine can recognise.
- Dictation can show realtime text while you speak on the Streaming path, with
  an optional preference that keeps the live draft on even with cleanup or
  translation.
- Cleanup is a model selector with an explicit Off; dictation and translation
  engines sit in Quick controls beside the choices they belong to; Captions can
  start from its own pane.
- The app icon is the Dictus voice mark, rebuilt from a checked-in Icon Composer
  source; settings row buttons no longer all default to glass.
- The ship DMG keeps its volume icon after Finder layout.
- Signed ZIP and styled DMG are notarized and stapled.

DMG SHA-256: be5e2667c867d063a4473150ebb1f822095535f420fbfb60dd264bf8e489b5c2

ZIP SHA-256: 9c2b6cec68488ac3f9a3ea41414df5f7c7a5e830cc2a2691ac2a502cff9cf6dc

## What's new in 2.6.0

- Hy-MT2 is available as an optional CPU-based translation engine for its 37
  supported languages, with automatic fallback to MADLAD.
- Translation failures and model declines are handled separately; real failures
  are logged and repeated failures safely retire the broken engine.
- Press-to-talk now defaults to ⌥⌘Space, requires a real key chord, and is off
  on fresh installs while preserving existing users' choices.
- Subtitle export cues stay readable at 17 characters per second without
  overlapping later speech; dictation cleanup and caption language analysis are
  faster.
- Long dictations explain the recording limit, and fixes cover model cleanup,
  transcript-search performance, caption cue timing, and hotkey permission
  retries.
- Verified 547 tests across 69 suites; the signed ZIP and styled DMG are
  notarized and stapled.

DMG SHA-256: aab2fff596f559cd00a2a1fb9f09c19bafac17c867df2cc4d45f50d974ca3d71

ZIP SHA-256: f4dae16f6fcc1f8f9b6b4fd843669b365f83b595458ce6cd38e2d5d34192752d

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
