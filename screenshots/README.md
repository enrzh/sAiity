# Public screenshots

Freshly captured October 7, 2026 from the tagged **v2.6.5** app source, in a
disposable photography build with a separate bundle identifier and synthetic
example captions/transcripts. The application source and shipped release were
not modified. No audio was recorded and no model inference was run.

| File | Native surface |
| --- | --- |
| `captions.png` | Captions settings |
| `dictation.png` | Dictation settings |
| `transcripts.png` | Example saved-session library |
| `summary.png` | Example bilingual transcript and summary |
| `bubble.png` | Actual caption bubble displaying synthetic bilingual text |
| `icon.png` | Current app icon |

The app's existing `SAIITY_TEST_HOOKS` capture entry point was used in an isolated
copy of the release source. For photography only, windows use a readable light
appearance and a larger minimum height. ScreenCaptureKit photographs only that
process's own windows, retaining the native controls and materials. Images use
2× output dimensions; actual detail depends on the display's backing scale.
A temporary session-directory override prevents access to the user's transcript
library. The summary text is a fixture demonstrating the UI, not evidence of
model accuracy. The bubble uses the app's solid background setting for contrast.

For future refreshes, use the published release tag, a disposable app identity
and a temporary library. Capture settled native windows, not reconstructed
HTML or generated UI. Inspect every image for clipping and private data before
publication. Keep original aspect ratios. Older, unreferenced images remain for
historical links and are not presented as current screenshots.
