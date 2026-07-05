# Silk Screen Halftone

### Pure JavaScript CMYK Halftone Engine 鈥?Tri-color Screen Print Simulation

Turn any photo into a silk screen / pop art / Warhol-style halftone print. Real variable-size dots at proper screen angles. Zero dependencies. 100% client-side.

**Live Demo: https://2645149786-dotcom.github.io/silk-screen-halftone/**
**Try on ToolKnit: https://toolknit.com/tools/silk-screen.html**

---

## What This Is

This is a **real halftone engine**, not a Photoshop filter approximation.

Each pixel channel (red, blue, grey) is processed through a rotated halftone grid. Dots grow or shrink based on the intensity of that channel at that location 鈥?exactly how offset printing works.

- **Red channel** 鈥?rotated halftone grid (default 15 deg)
- **Blue channel** 鈥?rotated halftone grid (default 75 deg)  
- **Grey channel** 鈥?rotated halftone grid (default 45 deg)

The three channels are then composited with multiply blending on your chosen paper color.

## Features

- Real halftone dots 鈥?variable-size circular dots, not a pixelation shader
- Per-channel screen angles 鈥?30+ deg separation to eliminate moire patterns
- Adjustable LPI 鈥?lower = bigger dots (punk poster), higher = fine detail (offset print)
- Custom channel colors 鈥?red, blue, grey with full color picker support
- Paper background color 鈥?warm newsprint, pure white, black, or anything
- Individual channel preview 鈥?toggle between composite, red-only, blue-only, grey-only
- PNG export 鈥?one-click download at full resolution
- Zero dependencies 鈥?no npm, no framework, no CDN. One HTML file.
- 100% client-side 鈥?your image never leaves your device

## Quick Start

git clone https://github.com/2645149786-dotcom/silk-screen-halftone.git
open silk-screen-halftone/index.html

No build step. No npm install. Just open the file.

## How It Works

The core algorithm is in 3 functions totaling ~100 lines of code:

- generateHalftoneChannel() 鈥?creates halftone dots for one color channel
- compositeSilkScreen() 鈥?blends all three channels together with multiply blending
- renderSingleChannel() 鈥?previews one channel in isolation

## Why This Is Different

Most halftone tools online are just threshold filters 鈥?reduce to black/white dots or pixelate. This engine does the real thing: rotated screens per channel, variable dot radius proportional to intensity, and proper color separation.

## Related

- ToolKnit 鈥?89 free browser-based tools, full-featured version with bilingual support: https://toolknit.com
- ToolKnit GitHub: https://github.com/2645149786-dotcom/toolknit

## License

MIT 鈥?use it, fork it, ship it. See LICENSE.
