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
