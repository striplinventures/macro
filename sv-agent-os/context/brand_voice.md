# Brand Voice & System

**Source of truth:** the live site, `striplinventures.lovable.app` — Lovable
project `cf0c1f72-a498-4efb-88e1-fd1b4c121f77`, design tokens in
`src/styles.css`. When this file and that file disagree, the site wins and this
file gets updated. See `web_platform.md` for the rest of the site.

## Palette

The brand is **dark-first**. Near-black ground, one magenta accent, nothing else
competing.

| Token | Hex | Use |
|---|---|---|
| `--background` | `#070708` | The ground. Every surface starts here. |
| `--foreground` | `#F4F4F6` | Body text. Not pure white. |
| `--primary` | `#F235A0` | Vivid Magenta — the only accent. |
| `--primary-foreground` | `#000000` | **Text on magenta is black, never white.** |
| `--card` / `--muted` | `#0E0E10` | Raised surfaces. |
| `--secondary` | `#131316` | Secondary surfaces. |
| `--muted-foreground` | `#8A8A90` | Captions, labels, eyebrows. |
| `--border` | `rgba(244,244,246,0.10)` | Standard border. |
| `--hairline` | `rgba(244,244,246,0.14)` | The Swiss grid rules. |
| Magenta hover | `#FF4EB1` | Button hover only. |

Text selection is magenta ground with black text. There is no light theme — the
site commits to dark, and anything branded should too.

## Type

| Role | Stack |
|---|---|
| Display | `"Anton", "Helvetica Neue", Impact, sans-serif` |
| Display alt | `"Antonio", "Anton", "Impact", "Helvetica Neue", sans-serif` — the tighter cut used for the "GOT PFAS?" treatment |
| Body | `"DM Sans", "Helvetica Neue", Helvetica, Arial, sans-serif` |
| Mono | `"Space Mono", ui-monospace, monospace` |

Setting that carries the identity:

- **Display:** uppercase, `letter-spacing: 0.06em`, `line-height: 0.92`.
- **Display alt (Antonio):** weight 700, `letter-spacing: -0.045em`,
  `line-height: 0.82` — much tighter, used big.
- **Section eyebrow:** mono, 11px, `letter-spacing: 0.22em`, uppercase, muted.
- **Section number:** same, but magenta.
- **Label:** DM Sans, 12px, weight 500, `letter-spacing: 0.14em`, uppercase,
  muted.
- Body uses `font-feature-settings: "ss01", "cv11"`.

## Form language

**Swiss grid, sharp corners, hairline rules.** The layout is a 12-column
container, max 1280px, side padding `clamp(20px, 4vw, 48px)`, with hairline
borders dividing sections rather than cards floating on shadows.

- Radii are nearly square: 2px small, 4px medium, 6px large, 10px xl. Buttons use
  2px. Nothing is pill-shaped or heavily rounded.
- Primary button: magenta ground, **black** text, weight 700, uppercase,
  `letter-spacing: 0.04em`, 2px radius. Hover lifts 1px and shifts to `#FF4EB1`.
- Ghost button: transparent with a hairline border; hover turns the border and
  text magenta.
- Form inputs: **bottom rule only** — transparent background, no box, no radius.
  Focus turns the bottom rule magenta.
- Motion is restrained: a slow marquee, a fade-up on entry, a soft glow pulse on
  the primary CTA, and a water-drop/ripple animation on submit confirmation. All
  of it respects `prefers-reduced-motion`.

## Logo

`src/assets/sv-logo.png` in the site project (asset
`38a219e3-6175-492c-a75c-3489d6e167d3`) — the crowned flamingo-S with the upward
chrome V-arrow.

The wordmark is typographic and easy to reproduce anywhere: display face,
uppercase, `letter-spacing: 0.02em`, with **"Striplin" in foreground and
"Ventures" in magenta**.

## Tone

Direct, data-backed, locally-grounded. Lead with the PFAS and water-quality
facts, not a product pitch. Confident but not hypey. "Opportunity Creator," not
"salesman."

## Writing rules

- Short sentences. Say the thing, then stop.
- Use real local specifics — utility names, zip codes, measured ppb figures —
  instead of generic claims. The specifics are the credibility.
- Ask more than you assert, especially in rep-track outreach (see the NEPQ script
  in `../reps/skills/sales_script.md`).
- Labels and eyebrows are uppercase and letterspaced; body copy is not. Don't
  shout in paragraphs.
- No hype words, no urgency theater, no income-flexing.
- Never write anything implying a guaranteed income or return.

## Compliance overrides tone

Any public-facing content follows the Amway compliance rules in
`business_info.md` first: education before product, no income claims, no
independent branding of Amway products, engage rather than broadcast. If good
copy and compliance conflict, compliance wins and the copy gets rewritten.
