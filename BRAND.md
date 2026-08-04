# SyncMyLibs — Brand & Design Identity

The single source of truth for how SyncMyLibs looks and speaks outside the app.
(In-app design law lives in the app repo: `AI Audits/architecture-2026-07-31/DESIGN_LANGUAGE.md`.)

## Idea

**Libraries as physical cards, sync as an orbit.** Everything visual derives from
the app icon: white photo cards (your libraries), a ring of motion around them
(sync), an azure→indigo sky (macOS-native depth), one warm amber point (the sun
in the card's photo — and the only "act now" color we own).

## Color

| Token | Value | Role |
|---|---|---|
| Azure | `#52A6F8` | Brand primary; links, kickers, active accents |
| Indigo | `#1D47B8` | Depth partner in gradients; emphasis text (light mode) |
| Deep | `#16204F` | Darkest gradient stop; shadows' tint |
| Amber | `#FFC24A` | THE action color — download/buy CTAs only. Never decorative. |
| Amber ink | `#7A4D00` | Text on amber |
| Light bg / ink | `#F6F8FC` / `#131A33` | Page base, light |
| Dark bg / ink | `#0B1026` / `#EEF2FB` | Page base, dark |

Rules: gradients are always azure→indigo(→deep), light from the top. Amber
appears at most twice per screen. Success/error semantics follow macOS system
colors, never brand colors.

## Type

- **Display / headlines:** New York (`ui-serif`), weight 600, tight leading
  (1.05–1.15), italic for the emotional word. Fallback Georgia.
- **Body / UI:** SF Pro (`-apple-system`), 17px base.
- **Technical facts:** SF Mono (`ui-monospace`), small caps kickers with
  0.1em+ tracking. Facts and system requirements are ALWAYS mono.

Rationale: every reader of this product is on an Apple device; using Apple's
own faces renders the brand in the platform's voice with zero webfont weight.

## Materials & depth

Glass cards: translucent surface + `backdrop-filter: blur(18-22px) saturate(1.4)`
+ 1px hairline border. Atmosphere: fixed radial azure washes + ~3% noise grain.
Shadows are indigo-tinted, long and soft (`0 24px 60px -24px`), never gray.

## Motion

One staged entrance per page (staggered rise, 80ms steps). The sync ring
rotates slowly (≥12s period) — the only perpetual motion allowed. Scroll
reveals via CSS scroll-driven animations behind `@supports`, and everything
respects `prefers-reduced-motion`.

## Voice

Problem-first, confident, zero hype. Name the constraint, then the removal of
it ("Photos opens one library. You have more than one."). Numbers over
adjectives. Honesty is a feature: the comparison table concedes PowerPhotos'
App Store presence; the safety section explains, never reassures vaguely.
Words we never use: "supercharge", "seamless", "blazingly", "AI-powered".

## Icon

Generated parametrically in the app repo: `Tools/IconGen/generate-icon.swift`
(all sizes from geometry; `--layers` mode emits flat Liquid Glass layers).
Site uses the 512px render as `/icon.png` (favicon, touch icon, og:image).
Regenerate there — never hand-edit exports.
