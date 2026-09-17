# Decisions

Choices made while building the deck that are not in the README or slide
backmatter.

## Photos

- `IMG_1486` (grinding, sparks) opens; `IMG_1483` (fitting the fender on
  the finished car) closes. Morgan picked the order.
- Both are portrait and stay portrait, shown at `max-height: 620px` on the
  black slide with space either side. Cropping to landscape would have cut
  either the car or him.
- Resized to 1400px tall, JPEG quality 85, EXIF stripped (`-strip`, which
  removes GPS). Source files stay in `~/Downloads`; only the resized copies
  are in the repo.
- Named `sergey-grinding.jpg` and `sergey-fender.jpg` rather than the
  camera numbers.

## Check engine light

- Drawn as a single SVG path, the ISO-style engine silhouette: head bump
  top-left, fan bar left, exhaust stub right, two feet. `cel-on.svg` is
  amber `#ffb000` with a blurred copy behind it for glow; `cel-off.svg` is
  `#262626` with a faint stroke so the shape is still visible unlit.
- Two files rather than one SVG with a class toggle, so they work as plain
  `<img>` tags and the off state needs no script.
- Logo composites will be a logo image with a small `cel-on.svg` positioned
  over one corner in HTML, so there is one light asset and no per-logo
  composite files.

## Logos

- Brand marks (Python, npm, Go, Docker) come from Simple Icons 15.22.0
  (CC0-1.0) via the jsDelivr npm mirror, with `fill="#e6e6e6"` added so they
  read on the black theme. VS Code is no longer in Simple Icons, and "VS Code" alone
  named a product rather than the thing that happened. That slide now
  uses the light over plain text ("xz", "IDE extensions") and has no
  wordmark files.
- Terminal and the skills sparkle are hand-drawn so they stay generic rather
  than pointing at a shell or a vendor.
- The light is composited in HTML (`.logo` wrapper, `.cel` positioned over
  the bottom-right corner), not baked into per-logo files. One light asset,
  and the row on the last slide goes dark by swapping the file name.
- The ecosystem slot is a `.logo.cluster`: Python large, npm and Go small in
  the top corners, one light for the group.

## Export

- devopsdays accepts PPT or static images and combines ignites into one
  PowerPoint. The deck exports as one full-bleed 1920x1080 PNG per slide
  inside a 16:9 PPTX, with each slide's narration as PowerPoint speaker
  notes. Images avoid font substitution; notes are how the narration gets
  onto the venue's confidence monitor.
- decktape renders the PNGs and a PDF; `mkpptx` (python-pptx) assembles the
  PPTX. Both come from nixpkgs through the flox environment.
- Reveal moved from its 960x700 default to 1280x720 so the render matches
  the venue's aspect ratio. Sizes were then scaled up about 30% because the
  4:3 design filled less than half the 16:9 frame.
- The off state of the light was brightened (`#343434` fill, `#666`
  stroke) after the first render showed it nearly invisible.
