# sAiity Public Pages Homepage

## Status

Draft for review. The public repository remains the
download and product surface; the private source repository is out of scope.

## Goal

Replace GitHub Pages' README wrapper with a deliberate product homepage at
`/`, while keeping `README.md` useful as the repository fallback and leaving
`privacy.html`, `en/privacy.html`, and `appcast.xml` unchanged.

The page should feel like an Apple product page for a small, serious Mac tool:
quiet, precise, typographic, and useful. It must not use gradients, animated
backgrounds, glassmorphism, decorative blobs, stock imagery, or marketing
claims that are not supported by the app.

## Selected direction

Direction A, the editorial document treatment:

- Warm white or system light surface with a restrained dark ink palette.
- A large serif product statement balanced by compact sans-serif metadata.
- Thin rules and generous whitespace create structure instead of cards.
- Real sAiity screenshots act as the visual proof of the product.
- A small cyan accent is reserved for links, status, and the primary action.
- Motion is optional and limited to reduced-motion-safe micro-interactions;
  there is no fading background or continuous decorative animation.

## Information architecture

1. **Header**
   - sAiity wordmark on the left.
   - Text links to `Features`, `Privacy`, and `GitHub` on desktop.
   - Compact menu or wrapped links on narrow screens; no opaque hamburger
     control without a working menu.

2. **Hero**
   - Eyebrow: `sAiity for Mac`.
   - Headline: a direct product statement, for example
     `Speech on the machine, not in the cloud.`
   - Supporting line: live captions, translation, transcripts, and
     press-to-talk dictation for macOS.
   - Primary action: `Download for Mac`, linking to the current GitHub Release
     asset or release page.
   - Secondary action: `View on GitHub`.
   - Small requirements line: `macOS 26 or later · Apple Silicon`.

3. **Product proof**
   - A full-width, unframed caption-bubble screenshot first, because it shows
     the product in use immediately.
   - A compact row or grid of the four existing settings screenshots, each with
     a short factual label: Captions, Models, Transcripts, Dictation.
   - Images must use the existing files in `screenshots/`; do not generate
     replacement artwork for the product UI.

4. **Capabilities**
   - Four concise rows for Captions, Translation, Dictation, and Transcripts.
   - Copy should match the verified README capabilities and remain scannable.
   - Prefer a ruled list with one accent marker per row over nested cards.

5. **Privacy and local processing**
   - A short, prominent statement: no account, tracking, or audio upload.
   - Explain that recognition, translation, dictation, and saved transcripts
     run locally, with the microphone behavior accurately qualified.
   - Link to German and English privacy pages.

6. **Requirements and release**
   - State macOS 26+ on Apple Silicon.
   - Link to the current release and Sparkle appcast.
   - State that Windows is not supported.

7. **Footer**
   - aiity link, GitHub link, privacy links, and a compact product descriptor.

## Content rules

- Keep the page factual and aligned with `README.md`.
- Do not claim open-source availability; the implementation source is private.
- Do not expose credentials, signing details, or internal release operations.
- The download link must point to the current public release surface, not a
  stale version hardcoded in more than one place if the repository already has
  a canonical value available.
- Preserve the existing appcast URL and privacy URLs.
- Use English as the primary page language, with a clear link to German
  privacy content.

## Visual and interaction rules

- Use system fonts where possible: `-apple-system`, `BlinkMacSystemFont`, and
  standard fallbacks. A restrained editorial serif may be used for the hero
  headline only.
- Use a content width that remains comfortable on wide screens and 20px
  minimum side padding on small screens.
- Keep links and buttons high contrast with visible keyboard focus states.
- Use semantic landmarks, one `h1`, meaningful `alt` text, and visible skip
  navigation if the page grows beyond the hero.
- Preserve image aspect ratios and avoid cropping screenshots that contain
  readable UI.
- Provide a dark-mode variant through `prefers-color-scheme`, but keep the
  light editorial treatment as the default product impression.
- Respect `prefers-reduced-motion`; default interactions must remain complete
  without animation.

## Non-goals

- No change to the private source checkout.
- No change to the appcast feed, privacy pages, release artifacts, or app
  behavior.
- No JavaScript framework, build step, external font, analytics, cookie, or
  remote runtime dependency.
- No repository-wide README rewrite as part of the homepage implementation.
- No fabricated screenshots, testimonials, metrics, or feature claims.

## Acceptance criteria

- Visiting `https://enrzh.github.io/sAiity/` renders the custom homepage rather
  than GitHub's README template.
- The primary `Download for Mac` action reaches the current public release.
- The secondary GitHub action reaches `https://github.com/enrzh/sAiity`.
- All five existing screenshots load from relative paths and have useful alt
  text.
- Privacy and appcast links resolve to the existing repository pages.
- The layout is readable at mobile width and wide desktop width without
  overlap, clipped text, or horizontal scrolling.
- Light and dark system appearances remain legible; keyboard focus is visible;
  reduced motion does not remove content.
- The site contains no external scripts, fonts, analytics, or gradient/fade
  background treatment.
- A local server screenshot review is performed at representative desktop and
  mobile viewports before committing.
