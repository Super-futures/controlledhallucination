# Controlled Hallucination

A short experimental film, in HTML, on predictive perception, salience, and the inferential structure of ordinary cognition.

> The brain never directly meets the world. It receives fragments, and infers what they mean.

The piece runs ~5 minutes across four acts. It's not a neuroscience explainer. It's a slow visual essay built on the idea that perception is itself a *controlled hallucination* — and that what we call psychosis may be an altered regime of the same machinery, not a break from it.

---

## Viewing

Open `Controlled Hallucination - standalone.html` in any modern browser. It's a single self-contained file — no server, no build step, no internet connection required after first load. Works offline.

If you'd prefer to run from source, open `Controlled Hallucination.html` instead; the standalone is just that file with its dependencies inlined.

**Headphones recommended.** The soundtrack is a slow ambient drone synthesized in Web Audio. It needs the initial click on **begin** to start the audio context.

### Controls

| | |
|---|---|
| **Space** | play / pause |
| **← →** | seek ±5 seconds |
| **1 2 3 4** | jump to act |
| **timeline** | scrub anywhere |
| **tweaks icon** (top-right) | open the tweaks panel |

---

## Structure

| Act | ~Time | What's happening |
|---|---|---|
| **1 · Ordinary** | 0:00–1:00 | Predictive processing as the baseline. Fragments arrive; the brain completes them. Many possibilities resolve into one. |
| **2 · Salience** | 1:00–2:30 | Weak correlations begin to feel meaningful. Some signals weigh more than others. The world starts gently over-signifying itself around your attention. |
| **3 · Overbinding** | 2:30–4:00 | Inferential amplification escalates. Patterns within patterns. Precision weighting becomes unstable. Audio–visual correspondences misalign. |
| **4 · Return** | 4:00–5:00 | The opening shot returns, subtly altered. A persistent confidence ring now marks what was hidden inference all along. |

Eleven shots in total. Visuals partially predict sounds in Act 1; that coupling drifts in Acts 2–3 and re-aligns in Act 4 — the audience is invited to do predictive modelling on the film itself.

---

## Tweaks

A small panel exposes:

- **palette** — graphite (neutral) · moss (Tarkovsky-forest) · iodine (sepia archive) · noctis (midnight indigo) · phosphor (oscilloscope green). Default is moss.
- **intensity** — grain, haze, density
- **salience amplification** — how much the cursor warps the world
- **temperature** — warm ↔ cool tint
- **speed** — playback pace
- **soundtrack** / **captions** — on/off
- **typeface** — serif + mono, mono only, serif only

Settings persist while the page is loaded; they reset on refresh.

---

## Project layout

```
Controlled Hallucination.html       — entry point (loads the .jsx files)
Controlled Hallucination - standalone.html  — bundled single-file build (~2MB)

film.jsx        — timeline, controls, palettes, tweaks plumbing
motifs.jsx      — shared visual atoms: ShotCanvas, Caption, drawPoint, ConfidenceRing
shots-act12.jsx — Acts 1 & 2 (six shots)
shots-act34.jsx — Acts 3 & 4 (five shots)

audio.js        — Web Audio drone engine (slow pads, soft pings, granular whispers)
grain.js        — persistent film-grain canvas overlay
tweaks-panel.jsx — generic floating tweaks panel
```

Each shot is a small React component that renders to a full-bleed canvas (procedural motion) plus an optional SVG overlay (diegetic labels, confidence rings) plus essayistic subtitle captions. Shots are crossfaded with a 1.6-second overlap.

---

## Visual & sonic intent

The brief was explicit: **no glitch horror, no TED-Talk energy, no Apple-commercial polish, no clinical neuroscience aesthetics.** Schizophrenia is not framed as exotic pathology. It's introduced — late — as instability within processes already fundamental to all perception.

- **Visuals:** procedural perceptual fields, probabilistic overlays, salience heatmaps, recurring abstract motifs (smudges, triangles, rings) that drift across acts. No depicted faces, hospitals, or psychiatric imagery.
- **Motion:** confidence oscillation, lingering afterimages, asynchronous drift, recursive overbinding — designed to model cognition itself, not glitch.
- **Sound:** slow ambient guitar-like pads, soft harmonic saturation, granular susurration. The film grows denser and less stable during salience amplification but remains emotionally beautiful, not frightening.
- **Type:** EB Garamond italic for narration; JetBrains Mono uppercase for diegetic system labels.

---

## License

MIT.
