# sAiity Public Pages Homepage Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox syntax for tracking.

**Goal:** Replace GitHub Pages' README wrapper with a polished, factual sAiity homepage that leads with the current Mac download and proves the product with real screenshots.

**Architecture:** Add one dependency-free index.html at the repository root. Keep structure and CSS together so GitHub Pages serves it directly without a build step, JavaScript bundle, external font, analytics, or runtime service. Preserve README.md, both privacy pages, and appcast.xml as separate repository surfaces.

**Tech Stack:** Semantic HTML5, CSS custom properties in OKLCH, system fonts, responsive CSS Grid/Flexbox, GitHub Pages, existing PNG/JPEG screenshots.

## Global Constraints

- The public repository remains the download and product surface; implementation source stays private.
- Use the approved Direction A editorial-document treatment: restrained light surface, strong typography, thin rules, and real product imagery.
- No gradients, animated backgrounds, fading backgrounds, glassmorphism, decorative blobs, stock imagery, external fonts, external scripts, analytics, cookies, or fabricated claims.
- The primary action is Download for Mac; View on GitHub is secondary.
- State macOS 26 or later, Apple Silicon, and that Windows is not supported.
- Preserve existing privacy and appcast URLs; do not modify privacy.html, en/privacy.html, or appcast.xml.
- Support keyboard focus, meaningful image alt text, dark appearance, reduced motion, and WCAG 2.2 AA contrast.
- Verify the rendered page at desktop and mobile widths before publishing.

---

## File Map

- Create: /Users/enrico/Documents/GitHub/saiity-public/index.html — complete GitHub Pages homepage.
- Create: /Users/enrico/Documents/GitHub/saiity-public/docs/superpowers/plans/2026-08-24-saiity-public-pages-homepage.md — the implementation plan for this change.
- Preserve: /Users/enrico/Documents/GitHub/saiity-public/README.md — repository fallback/documentation.
- Preserve: /Users/enrico/Documents/GitHub/saiity-public/privacy.html — German privacy policy.
- Preserve: /Users/enrico/Documents/GitHub/saiity-public/en/privacy.html — English privacy policy.
- Preserve: /Users/enrico/Documents/GitHub/saiity-public/appcast.xml — Sparkle feed.
- Reuse: /Users/enrico/Documents/GitHub/saiity-public/screenshots/ — product evidence.

## Task 1: Add the semantic homepage structure

Files:
- Create: /Users/enrico/Documents/GitHub/saiity-public/index.html

Interfaces:
- Browser entry: /index.html at repository root.
- Release action: https://github.com/enrzh/sAiity/releases/tag/v2.2.4.
- Repository action: https://github.com/enrzh/sAiity.
- Relative assets: screenshots/01-bubble.png, 02-subtitles.png, 03-models.png, 04-library.png, 05-dictation.png.

- [ ] Step 1: Confirm the root entry is absent

Run:

    test ! -e index.html
    git status --short --branch

Expected: the first command succeeds; only known local .superpowers/ state is untracked.

- [ ] Step 2: Add the document shell and factual content

Create index.html with UTF-8 metadata, responsive viewport, title "sAiity — Speech on the machine", a factual description, and no script or external stylesheet. Use one h1, a skip link, a header/nav, and sections in this order: hero, product proof, capabilities, privacy, release, footer.

The hero must contain:

    <p class="eyebrow">sAiity for Mac</p>
    <h1 id="hero-title">Speech on the machine, not in the cloud.</h1>
    <p class="hero-lede">Live captions, translation, transcripts, and press-to-talk dictation for macOS.</p>
    <a class="button button-primary" href="https://github.com/enrzh/sAiity/releases/tag/v2.2.4">Download for Mac</a>
    <a class="button button-secondary" href="https://github.com/enrzh/sAiity">View on GitHub</a>
    <p class="requirements">macOS 26 or later · Apple Silicon · Windows not supported</p>

The proof section must use all five existing screenshot paths with width and height attributes, useful alt text, and captions: the bubble image first, then Captions, Models, Transcripts, and Dictation. The capabilities section must contain the four factual README capabilities. The privacy section must link to privacy.html and en/privacy.html. The release section must link to the v2.2.4 release and relative appcast.xml. The footer must link to https://aiity.de, GitHub, and privacy.

- [ ] Step 3: Validate structure and assets

Run:

    python3 - <<'PY'
    from html.parser import HTMLParser
    from pathlib import Path
    source = Path("index.html").read_text()
    HTMLParser().feed(source)
    assert source.count("<h1") == 1
    for name in ("01-bubble.png", "02-subtitles.png", "03-models.png", "04-library.png", "05-dictation.png"):
        assert Path("screenshots", name).exists(), name
    print("HTML structure and screenshot assets verified")
    PY
    git diff --check

Expected: the success line prints and git diff --check is silent.

- [ ] Step 4: Commit the semantic shell

    git add index.html
    git commit -m "feat: add custom public homepage shell"

## Task 2: Apply the approved visual system and responsive behavior

Files:
- Modify: /Users/enrico/Documents/GitHub/saiity-public/index.html inside head before head close.

Interfaces:
- CSS classes are the classes from Task 1; no JavaScript or runtime dependency is introduced.
- Light mode is default; prefers-color-scheme: dark remaps the same tokens.
- Content remains complete with prefers-reduced-motion: reduce.

- [ ] Step 1: Add the token block and base rules

Use one style block and start with these exact tokens:

    :root {
      color-scheme: light;
      --page: oklch(0.985 0.004 220);
      --surface: oklch(0.965 0.008 220);
      --ink: oklch(0.205 0.018 220);
      --muted: oklch(0.46 0.018 220);
      --line: oklch(0.86 0.014 220);
      --accent: oklch(0.62 0.145 195);
      --accent-ink: oklch(0.22 0.035 210);
      --shell: min(1120px, calc(100% - 40px));
      --serif: Iowan Old Style, Baskerville, Times New Roman, serif;
      --sans: -apple-system, BlinkMacSystemFont, "SF Pro Text", "Helvetica Neue", sans-serif;
    }
    @media (prefers-color-scheme: dark) {
      :root {
        color-scheme: dark;
        --page: oklch(0.19 0.015 220);
        --surface: oklch(0.235 0.018 220);
        --ink: oklch(0.94 0.012 220);
        --muted: oklch(0.74 0.018 220);
        --line: oklch(0.38 0.018 220);
        --accent: oklch(0.76 0.13 195);
        --accent-ink: oklch(0.16 0.02 220);
      }
    }
    *, *::before, *::after { box-sizing: border-box; }
    body { margin: 0; background: var(--page); color: var(--ink); font: 16px/1.6 var(--sans); text-wrap: pretty; }
    .shell { width: var(--shell); margin-inline: auto; }
    h1, h2 { text-wrap: balance; }
    a:focus-visible, .button:focus-visible { outline: 3px solid var(--accent); outline-offset: 4px; }

- [ ] Step 2: Add layout and responsive rules

Implement these structural rules and complete the selectors needed by the Task 1 markup:

    .hero { padding-block: clamp(72px, 13vw, 168px) clamp(72px, 10vw, 128px); }
    h1 { max-width: 10ch; margin: 0 0 26px; font: 400 clamp(50px, 8vw, 96px)/0.98 var(--serif); letter-spacing: -0.035em; }
    .section-heading, .privacy-inner, .release { display: grid; grid-template-columns: minmax(0, 1fr) minmax(240px, .8fr); gap: 48px; }
    .proof, .capabilities, .release { padding-block: clamp(72px, 10vw, 128px); border-top: 1px solid var(--line); }
    .product-views { display: grid; grid-template-columns: repeat(4, minmax(0, 1fr)); gap: 16px; }
    .capability-list article { display: grid; grid-template-columns: minmax(150px, .45fr) minmax(0, 1fr); gap: 32px; padding-block: 22px; border-bottom: 1px solid var(--line); }
    @media (max-width: 760px) {
      :root { --shell: min(100% - 32px, 1120px); }
      .section-heading, .privacy-inner, .release { grid-template-columns: 1fr; gap: 18px; }
      .product-views { grid-template-columns: repeat(2, minmax(0, 1fr)); gap: 12px; }
      .capability-list article { grid-template-columns: 1fr; gap: 6px; }
    }
    @media (max-width: 420px) {
      .actions { align-items: stretch; flex-direction: column; }
      .button { width: 100%; }
      .product-views { grid-template-columns: 1fr; }
    }
    @media (prefers-reduced-motion: reduce) {
      html { scroll-behavior: auto; }
      .button { transition: none; }
    }

Use thin full-width rules, no colored side stripes, one-pixel screenshot boundaries, pill buttons only for the two actions, visible focus, and no border-plus-large-shadow card treatment. Complete the theme selectors for header, nav, typography, screenshots, privacy band, release links, and footer using only solid token values.

- [ ] Step 3: Run anti-pattern and asset checks

    git diff --check
    ! rg -n 'linear-gradient|radial-gradient|backdrop-filter|<script|fonts\.googleapis|unsplash|analytics|telemetry' index.html
    test "$(rg -n 'screenshots/(01-bubble|02-subtitles|03-models|04-library|05-dictation)\.png' index.html | wc -l | tr -d ' ')" = 5

Expected: every command succeeds and the forbidden-pattern search prints nothing.

- [ ] Step 4: Commit the styled homepage

    git add index.html
    git commit -m "feat: style public Pages homepage"

## Task 3: Verify rendering and publish the Pages homepage

Files:
- Verify: /Users/enrico/Documents/GitHub/saiity-public/index.html.
- Verify unchanged: /Users/enrico/Documents/GitHub/saiity-public/README.md, privacy.html, en/privacy.html, appcast.xml.

Interfaces:
- Local origin: http://127.0.0.1:4173/.
- Deployed origin: https://enrzh.github.io/sAiity/.

- [ ] Step 1: Start a local static server

    python3 -m http.server 4173

Expected: 127.0.0.1:4173 serves index.html.

- [ ] Step 2: Inspect real rendered screenshots

Use the available browser screenshot tool at 1440 x 1100 light, 390 x 844 light, and 1440 x 1100 dark. Inspect the images themselves. Verify the headline fits, the first product screenshot is visible in the first scroll, actions and nav do not overlap, captions remain attached to images, no horizontal scrollbar appears at 390px, and dark-mode body/link text remains readable.

- [ ] Step 3: Verify local routes and assets

    for path in / /screenshots/01-bubble.png /screenshots/02-subtitles.png /screenshots/03-models.png /screenshots/04-library.png /screenshots/05-dictation.png /privacy.html /en/privacy.html /appcast.xml; do
      curl --fail --silent --show-error --head "http://127.0.0.1:4173$path" >/dev/null || exit 1
    done
    printf '%s\n' 'Local homepage routes and assets verified'

Expected: every request succeeds and the success line prints.

- [ ] Step 4: Verify support files were not changed

    git diff origin/main -- README.md privacy.html en/privacy.html appcast.xml
    git diff --check
    git status --short --branch

Expected: the support-file diff is empty and only intended website files plus known local tool state appear.

- [ ] Step 5: Push and verify GitHub Pages

    git push origin main
    curl --fail --silent --show-error https://enrzh.github.io/sAiity/ | rg -q 'Speech on the machine, not in the cloud\.'
    printf '%s\n' 'GitHub Pages homepage is serving the custom entry point'

Expected: push succeeds and, after Pages propagation, the deployed HTML contains the new hero copy. Retry after propagation if the first request still returns the README wrapper; do not claim deployment until the new text is observed.

- [ ] Step 6: Stop local tooling and confirm final state

Stop the local server and brainstorming companion after visual verification. Remove only task-generated temporary state under /Users/enrico/Documents/GitHub/saiity-public/.superpowers/; do not touch sibling projects or tracked source. Then run git status --short --branch and git log -5 --oneline. Expected: no unintended website artifacts remain and the published branch is synchronized with origin/main.
