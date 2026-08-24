# Broetry Foundry

An industrial control panel that manufactures the LinkedIn post beginning
*"I just built ___ without knowing how to code."*

One self-contained `index.html`. No build step, no dependencies, no network calls.

## Run

```bash
python3 -m http.server 4711
```

Then open http://localhost:4711. Opening `index.html` directly via `file://` also
works — the only remote asset is Google Fonts, which falls back cleanly offline.

## What it does

- **Type a SaaS name** and every post routes through the beat the genre exists for:
  *"Now everyone is in my DMs asking the same thing: why should I use Zaply?"*
- **Absurdity dial**, five stops: Mildly Insufferable → Thought Leader → Fully
  Unhinged → Broetry Singularity → Ascended
- **Nine toggles** — revenue screenshot, broetry line breaks, emoji bullets,
  unprompted crying, aggressive humility, hashtag avalanche, and friends
- **Fabricated revenue chart** — a payments-dashboard screenshot drawn from the
  same numbers the post brags about, so the text and the graph always agree
- **Cringe PSI gauge** that pins past red at maximum
- **Share links** that reproduce the exact post, not just the settings

## How the share links work

Every draw runs through one seeded PRNG (mulberry32) rather than `Math.random`,
and the seed rides in the URL hash alongside the controls:

```
#s=Kestrel.dev&t=a+budgeting+app+that+shouts&n=Prescott+Ravenscroft&d=4&f=111111011&k=zzz9q1
```

`s`/`t`/`n` are the text fields, `d` the dial, `f` nine toggle bits, `k` the seed.
Opening the link rebuilds that exact unit — post text, author, chart geometry and
all. Replaying clears the generator's no-repeat memory first, since output
otherwise depends on draw history as well as the seed.

## Design

The visual system combines two references: **Hyperstudio** supplies the chassis
(obsidian canvas, 1px hairline structure, weight-400 editorial voice, 8px radii,
no shadows) and **Caldera** supplies what's molten inside it (Ember accent,
halftone dot fields, 800px pill controls, ultrabold compressed display type).

The console stays Hyperstudio-dark in both themes, which is what makes its Pulse
Green and Compass Gold legal — both are dark-only colours in that system. The
theme switches the room the machine stands in and the paper it prints on.

Type: Anton (display), DM Sans (body), IBM Plex Mono (labels and meta).

## Note

It's a parody. Every name, company, metric, revenue chart and moment of personal
growth is fabricated by a random number generator with no inner life. Nothing is
posted anywhere and no network is contacted — "Post it for real" is a placebo.
