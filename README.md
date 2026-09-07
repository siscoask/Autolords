# AUTOLORDS — Engr. Jidey

A single-page portfolio site for AUTOLORDS, told in first person by Engr. Jidey — gear and automatic-transmission specialist. No photography, no certifications wall, no filler stats. The site is built entirely from typography, interactive diagrams, and a custom notation system.

**Live file:** `autolords-v4.html` (latest version — self-contained, no build step, no dependencies to install)

---

## What this is

Not a standard "Hero → About → Services → Contact" business site. The structure follows a personal narrative instead:

| Mark | Section | Anchor |
|------|---------|--------|
| `A.01 ↻` | I work with gears — opening statement + interactive planetary-gear diagram | `#gears` |
| `A.02 ♀` | In plain terms — customer problem → diagnosis → fix, in a flowing editorial layout | `#plain` |
| `A.03 △` | This is how I work — the five-stage process, shown as one connected rail | `#process` |
| `A.04 ♄` | The bench — the tools (SolidWorks, CNC, Bosch diagnostics, CAD/CAM) | `#tools` |
| `A.05 →` | What I've built — four case studies, archive-style, each with its own annotated diagram | `#work` |
| `A.06 +` | Ready to look at yours? — the booking form | `#book` |

The six glyphs (`↻ ♀ △ ♄ → +`) are a deliberate notation system, not decoration — each one is unique to its section and repeats consistently so it reads as a signature by the time someone's scrolled the whole page.

---

## How to open / deploy

It's one HTML file with everything inlined (CSS in `<style>`, JS in `<script>`, Google Fonts + nothing else loaded externally). To use it:

- **Preview locally:** just double-click the file, or drag it into a browser tab.
- **Deploy:** upload it as-is to any static host — Vercel, Netlify, GitHub Pages, or a plain web server. Rename it to `index.html` for most hosts to serve it as the homepage.

No `npm install`, no build step, no framework.

---

## Editing the content

Everything is plain text inside the HTML — search for the English copy directly, there's no CMS or data file. A few things you'll likely want to change:

- **WhatsApp number** — appears in two places: the "Connect"/footer link (`https://wa.me/+2347085187692`) and inside the `sendBooking()` function in the `<script>` at the bottom (`phone=+2347085187692`). Update both if the number changes.
- **Social links** — in the `<footer>`, the `.social-row` block: WhatsApp, TikTok, X, Instagram, Facebook. Swap the `href` values.
- **Booking service list** — the options inside `#selectList` in the "Ready to look at yours?" section. Add, remove, or rename `<div class="select-opt" data-value="...">` entries; `data-value` is what gets sent to WhatsApp.
- **Case studies** — each `.case` block under `#work` has its own copy, spec rows, and a small SVG diagram with one highlighted node + tag (`FAULT`, `DESIGNED`, etc). Copy an existing `.case` block as a template for a new one.

---

## The interactive gear diagram

In the opening section, the planetary-gear SVG (`#gearSvg`) is a real, simplified gear-train diagram: an outer ring gear, three planet gears, and a center sun gear. Hovering (desktop) or tapping (mobile/touch) each part updates the readout text below it. The logic lives in the `zoneInfo` object in the `<script>` — edit the `label`/`desc` strings there to change what each part explains.

---

## Design system notes

- **Palette:** graphite/near-black base (`--void`, `--panel`), one restrained blue accent (`--blue`) used only for interactive states, notation marks, and the diagram highlights.
- **Type:** Space Grotesk for display/headlines, IBM Plex Sans for body copy, IBM Plex Mono for all notation, labels, and technical annotations.
- **Background:** a fixed, very low-opacity SVG of concentric circles and construction lines (`#bgTech`) with a handful of softly pulsing points — meant to read as a technical drawing catching light, not a starfield or space theme.
- **Motion:** intentionally restrained — the five process steps light up in sequence as you scroll to them, the background pulses stay near-invisible, and everything respects `prefers-reduced-motion`.
- No emojis, no stock photography, no fabricated statistics or certifications anywhere in the copy — by design.

---

## Credit

Design & development — **Sisco Ask** ([siscoask.vercel.app](https://siscoask.vercel.app)) — set in the site footer.
