
<p align="center">
  <img src="https://img.shields.io/github/stars/2645149786-dotcom/silk-screen-halftone?style=for-the-badge&color=e63946" alt="stars">
  <img src="https://img.shields.io/github/license/2645149786-dotcom/silk-screen-halftone?style=for-the-badge&color=457b9d" alt="license">
  <img src="https://img.shields.io/badge/vanilla-js-yellow?style=for-the-badge" alt="vanilla js">
  <img src="https://img.shields.io/badge/zero-deps-brightgreen?style=for-the-badge" alt="zero deps">
  <img src="https://img.shields.io/badge/size-~15KB-lightgrey?style=for-the-badge" alt="size">
</p>

<h1 align="center">
  Silk Screen Halftone
</h1>

<h3 align="center">
  <i>Pure JavaScript CMYK Halftone Engine &mdash; Tri-Color Screen Print Simulation</i>
</h3>

<p align="center">
  Turn any photo into a silk screen / pop art / Warhol-style halftone print.<br>
  Real variable-size dots at proper screen angles. Zero dependencies. 100% client-side.
</p>

<p align="center">
  <a href="https://2645149786-dotcom.github.io/silk-screen-halftone/"><strong>Live Demo</strong></a>
  &nbsp;&middot;&nbsp;
  <a href="https://toolknit.com/tools/silk-screen.html"><strong>Full Version on ToolKnit</strong></a>
  &nbsp;&middot;&nbsp;
  <a href="#quick-start"><strong>Quick Start</strong></a>
</p>

<br>

---

## What Makes This Different

> Most "halftone" tools online are just **threshold filters** &mdash; reduce to black/white dots or pixelate.
> This engine does the **real thing**: rotated screens per channel, variable dot radius proportional to intensity, and proper color separation.

Each pixel channel (red, blue, grey) is processed through a **rotated halftone grid**. Dots grow or shrink based on channel intensity &mdash; exactly how offset printing separates CMYK plates.

<table>
<tr>
<td width="33%" align="center"><b>Red Channel</b><br>15&deg; screen angle</td>
<td width="33%" align="center"><b>Blue Channel</b><br>75&deg; screen angle</td>
<td width="33%" align="center"><b>Grey Channel</b><br>45&deg; screen angle</td>
</tr>
</table>

The three channels are composited with **multiply blending** on your chosen paper color &mdash; just like ink on newsprint.

---

## Features

<table>
<tr>
<td width="50%">

###  Core
- **Real halftone dots** &mdash; variable-size circular dots, not a pixelation shader
- **Per-channel screen angles** &mdash; 30&deg;+ separation eliminates moir&eacute; patterns
- **Adjustable LPI** &mdash; low = big dots (punk poster), high = fine detail (offset print)
- **Dot size scaling** &mdash; 0.3x to 2x multiplier for artistic control

</td>
<td width="50%">

###  Output
- **Custom channel colors** &mdash; full color picker for each channel
- **Paper color** &mdash; warm newsprint, pure white, black, any color
- **Channel preview** &mdash; toggle composite / red-only / blue-only / grey-only
- **PNG export** &mdash; one-click download at full resolution

</td>
</tr>
</table>

---

## Quick Start

```bash
git clone https://github.com/2645149786-dotcom/silk-screen-halftone.git
open silk-screen-halftone/index.html
```

That's it. No `npm install`. No build step. No framework. **One HTML file.**

---

## How It Works

The entire engine is ~100 lines of JavaScript in 3 functions:

```javascript
// 1. Walk rotated grid, sample channel intensity, draw dots
generateHalftoneChannel(srcData, channel, angle, lpi, dotScale)

// 2. Multiply-blend all channels on paper background
compositeSilkScreen(redChannel, blueChannel, greyChannel, width, height)

// 3. Preview single channel in isolation  
renderSingleChannel(halftoneData, color, width, height)
```

**Algorithm:**
1. Uploaded image is drawn to a hidden canvas
2. Each channel (red/blue/grey) iterates through a rotated dot grid
3. At each grid point, channel intensity is sampled &rarr; dot radius computed
4. All three channels are composited with multiply blending
5. Result is rendered to visible canvas and available for PNG export

---

## Architecture

```
index.html
  鈹溾攢鈹€ Inline CSS (no external stylesheets)
  鈹溾攢鈹€ Inline JS (no external scripts)
  鈹?    鈹溾攢鈹€ generateHalftoneChannel()  鈫?Core halftone math
  鈹?    鈹溾攢鈹€ compositeSilkScreen()      鈫?Multiply blend engine
  鈹?    鈹斺攢鈹€ renderSingleChannel()      鈫?Channel isolation
  鈹斺攢鈹€ Canvas API (HTML5, zero dependencies)
```

**Zero dependencies.** Not even a CDN. Works offline after first load.

---

## Related

- **[ToolKnit](https://toolknit.com)** &mdash; 89 free browser-based tools built with this engine and others. Full bilingual (EN/CH) support, no signup, no uploads.
- **[ToolKnit GitHub](https://github.com/2645149786-dotcom/toolknit)** &mdash; More open-source standalone demos and tool collection.

---

## License

MIT &mdash; use it, fork it, ship it, sell it. See [LICENSE](./LICENSE).

<br>

<p align="center">
  <sub>Built with love by <a href="https://toolknit.com">ToolKnit</a></sub>
</p>
