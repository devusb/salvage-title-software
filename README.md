# Salvage Title Software

**How we ship to ourselves** — Ignite-format lightning talk. 20 slides,
15 seconds each, auto-advanced. 5:00 flat.

## Running

```bash
flox activate --start-services     # http://localhost:3000
```

Or from inside an activated environment:

```bash
flox services start
flox services status
flox services stop
```

`npm install` once first if `node_modules` isn't present.

Press `Esc` for the overview.

## Practicing

```
http://localhost:3000/?practice
```

Nothing moves until you press `0` or click **start** in the corner. Then it
auto-advances every 15 seconds with a short tick, and shows a counter in the
corner: slide number, seconds left on this slide, total elapsed.

- `M` marks the end of your narration for the current slide. Press it on your
  last word. If you are still talking when the slide advances, press `M` when
  you finish and it counts against the slide you overran.
- `P` pauses and resumes (red outline while paused).
- `R` shows the report early; it appears on its own after the last slide.
- `0`, or the button in the corner, starts the run, or restarts it from slide one.

The report is one line per slide: seconds spoken, margin against 15, and
`tight` or `OVER`. Copy it and paste it back to get graded on pacing.

Press `S` for the speaker view if you also want the notes on screen. Without
`?practice` nothing ever advances on its own.

## Exporting

devopsdays wants exactly 20 slides as PPT or static images; they combine all
ignites into one PowerPoint and auto-advance it. The deck exports as one
full-bleed 1920x1080 image per slide with the narration in the speaker
notes, so nothing depends on fonts and the notes reach the confidence monitor.

```bash
flox services start
cd out && decktape reveal http://localhost:3000/ salvage-title-software.pdf \
  --size 1920x1080 --screenshots --screenshots-directory png \
  --screenshots-size 1920x1080 && cd ..
./mkpptx out/png out/salvage-title-software.pptx
```

Outputs in `out/` (ignored by git): the PDF, `png/` with one image per slide,
and the PPTX. Run decktape from inside `out/`; it builds the screenshot path
from the PDF path. `mkpptx` reads each slide's `Note:` text from `slides/*.md`
in order and refuses to run if the image and note counts differ.

Reveal is set to 1280x720 so the render is 16:9 like the venue deck.

## Structure

20 slides, all static, 15 seconds each.

| File | Slides | Section |
|---|---|---|
| `00-title.md` | 1 | Title, name, intro narration |
| `01-father-in-law.md` | 2 | The photo, the light |
| `02-pivot.md` | 2 | Production (light off), ours (four lit) |
| `03-bin.md` | 3 | Pattern 1: shell scripts (method, jank, risk) |
| `04-language.md` | 3 | Pattern 2: language ecosystem tooling (method, jank, risk) |
| `05-container.md` | 3 | Pattern 3: the container (method, jank, risk) |
| `06-skills.md` | 3 | Pattern 4: skills and MCP (method, jank, risk + bookend) |
| `07-take-stock.md` | 1 | xz and Nx Console |
| `08-close.md` | 2 | Him (kids moved away), us dark + contact |

Every pattern gets three slides: the logo with the check engine light plus
a short code block showing the artifact (script, README, Dockerfile, SKILL.md)
with a caption saying where it lives, then **Jank**, then **Risk**, each three bullets of
two to six words. The why lives in the narration and is always a real reason.
Jank is what's broken. Risk is what's exposed.

The close is him (photo), then us with the lights off and the contact line.
Lighthearted; the metaphor is never explained and nothing is asked of the
room.

Pattern 1 and pattern 4 are the same pattern; the last bullet of the skills
risk slide is "it's the shell script again."

## Word budget

Fifteen seconds is about 40 spoken words and about 3 seconds of reading.

- On screen: a title and at most ~10 words. Jank and risk slides are three
  bullets of two to six words. Ignite guidance is one idea per slide and no
  more than about ten words; the audience cannot read and listen at once.
- Narration: at most ~40 words per slide. The slide leaves without you.
- Anything cut from a slide that still matters goes in the narration, and
  anything cut from the narration is gone.

## Graphics to make

Nothing is a placeholder any more.
All slots are filled. Sources and files:

| Graphic | Used in | Notes |
|---|---|---|
| Father-in-law photo | `01`, `08` | Done: `sergey-grinding.jpg` (open), `sergey-fender.jpg` (close). |
| Check engine light | `01` lit, `02` unlit, and lit on every logo below | Done: `cel-on.svg`, `cel-off.svg`. Composites are a logo image plus a small `cel-on.svg` positioned over it, not baked files. |
| Terminal glyph | `02`, `03`, `08` | Drawn: `logos/terminal.svg`. |
| Python, npm, Go | `02`, `04`, `08` | Simple Icons (CC0), recolored `#e6e6e6`: `logos/python.svg`, `npm.svg`, `go.svg`. Python large, the other two small above it (`.logo.cluster`). |
| Docker whale | `02`, `05`, `08` | Simple Icons: `logos/docker.svg`. |
| Sparkle | `02`, `06`, `08` | Drawn: `logos/sparkle.svg`. Generic, not a vendor mark. |

The light is never baked into a logo. A `.logo` wrapper holds the mark and a
small `cel-on.svg` or `cel-off.svg` over its corner; `.logos` is the row of four.

## To verify

- [x] **IDE extension compromise.** Nx Console VS Code extension backdoored
      for 18 minutes on 2026-05-18; one GitHub employee installed it; ~3,800
      internal repos taken. Sources in `07` backmatter.
- [ ] **xz.** CVE-2024-3094, March 2024, liblzma, sshd via the systemd
      notification patch. One sentence.
- [ ] **`npx -y @scope/server`** with no version fetches latest.
- [x] **Claude Code plugin pinning** — authors can pin `ref`/`sha`/`version`;
      unpinned sources track the default branch. Slide says "unpinned by
      default", not "nothing is pinned". Sources in `06` backmatter.
- [x] **Codex** — `$skill-installer` pulls from repos; docs record no version.
- [x] **Language tooling claims** (`04`): `@latest`, npm lifecycle scripts,
      terraform state version, pip sdist vs wheel. Sources in the slide's
      backmatter. Install-hook example is Shai-Hulud or ua-parser-js, not
      event-stream.
- [ ] **`uv`** installs via `curl -LsSf https://astral.sh/uv/install.sh | sh` (in the
      backmatter only now; no longer on a slide).
- [x] **`mise`** installs via `curl https://mise.run | sh`. pyenv and nvm are
      the same shape. asdf is not (Go binary since 0.16); do not name it.
- [ ] **Sergejs knows he's on a slide.**

## If it runs long

There's nothing to cut; the format is fixed. If a slide's narration runs
past 15 seconds in practice, trim the narration, not the slide. The
narration in each `Note:` is already at the budget; treat it as a ceiling.

## Conventions

Matches `nixos-handheld-talk` and `nix-k8s-talk`, plus `mkpptx` alongside
the handheld deck's `mkgif`:

- Slide titles are flat descriptive labels, not jokes. Bits go in the
  speaker's mouth, not on the slide.
- No first person in slide text, except the label "Ours" on `02`. Commentary
  is voiceover.
- Speaker notes are the actual narration, in prose.
- Theme is `themes/flox-dark.css` (the Flox marketing deck theme) over reveal's
  black theme. Styling is inline per element. `index.html` carries heading sizes and the shared
  `.logo`, `.code`, `.path`, `.eyebrow`, and `ul.gap` rules and nothing else.
- No fragments. Every slide is static; a concept that needs a reveal gets
  another slide.
- Each slide file ends in a backmatter comment block with scope notes,
  graphics needed, and things to verify.
- Former employers stay in the narration if they appear at all, never on
  the slide.
