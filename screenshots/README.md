# Public screenshots

Freshly captured October 20, 2026 from the **Syllivra 2.7.0** release source
(tag `v2.7.0`, build 244), in a disposable photography build with a separate
bundle identifier and synthetic example captions/transcripts. The application
source and shipped release were not modified. No audio was recorded and no
model inference was run.

| File | Native surface |
| --- | --- |
| `captions.png` | Captions settings |
| `dictation.png` | Dictation settings |
| `transcripts.png` | Example saved-session library |
| `summary.png` | Example bilingual transcript and summary |
| `bubble.png` | Actual caption bubble displaying synthetic bilingual text |
| `icon.png` | Current app icon (unchanged since 2.6.5) |

The app's existing `SAIITY_TEST_HOOKS` capture entry point was used in an isolated
copy of the release source, extended there only to hold one real window open with
fixture content. Each window was then photographed by its window ID
(`screencapture -o -l`), keeping the native titlebar, controls and materials and
nothing else on screen. Settings windows use a readable light appearance at an
860 × 702 pt frame; the caption bubble keeps the system appearance with the
app's solid background setting for contrast. Images use 2× output dimensions.
A temporary session-directory override keeps the five example sessions away from
the user's transcript library. The summary text is a fixture demonstrating the
UI, not evidence of model accuracy, and the summary sheet is shown as if a
cleanup model were installed.

For future refreshes, use the published release tag, a disposable app identity
and a temporary library. Capture settled native windows, not reconstructed
HTML or generated UI. Inspect every image for clipping and private data before
publication. Keep original aspect ratios. Older, unreferenced images remain for
historical links and are not presented as current screenshots.
