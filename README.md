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

Press `S` for the speaker view (notes, clock, and a per-slide pacing timer
against the 15-second budget). `Esc` for the overview.

## Practicing

```
http://localhost:3000/?practice
```

Auto-advances every 15 seconds and plays a short tick on each advance.
`P` pauses and resumes (red outline while paused). Open the speaker view
alongside for the clock. Without `?practice` nothing ever advances on its
own.

## Structure

20 slides, all static, 15 seconds each.

| File | Slides | Section |
|---|---|---|
| `00-title.md` | 1 | Title, name, intro narration |
| `01-father-in-law.md` | 1 | The photo |
| `02-pivot.md` | 1 | The divide: production dark, ours lit |
| `03-bin.md` | 3 | Pattern 1: the `~/bin` script (method, jank, risk) |
| `04-language.md` | 3 | Pattern 2: language ecosystem tooling (method, jank, risk) |
| `05-container.md` | 3 | Pattern 3: the container (method, jank, risk) |
| `06-skills.md` | 3 | Pattern 4: skills and MCP (method, jank, risk + bookend) |
| `07-take-stock.md` | 1 | xz and VS Code |
| `08-close.md` | 4 | Him (kids moved away), us lit, us dark, thanks |

Every pattern gets three slides: the logo with the check engine light plus
how it's done and why, then **Jank**, then **Risk**, each three bullets of
two to six words. The why is always a real reason. Jank is what's broken.
Risk is what's exposed.

The close is him (photo), us with the lights on, us with the lights off,
thanks. Lighthearted; the metaphor is never explained and nothing is asked
of the room.

Pattern 1 and pattern 4 are the same pattern; the last bullet of the skills
risk slide is "it's the `~/bin` script again."

## Word budget

Fifteen seconds is about 40 spoken words and about 3 seconds of reading.

- On screen: a title and at most ~10 words. Jank and risk slides are three
  bullets of two to six words. Ignite guidance is one idea per slide and no
  more than about ten words; the audience cannot read and listen at once.
- Narration: at most ~40 words per slide. The slide leaves without you.
- Anything cut from a slide that still matters goes in the narration, and
  anything cut from the narration is gone.

## Graphics to make

Every slot is marked in the slides with a dashed `.placeholder` box that
says what goes there. None exist yet.

| Graphic | Used in | Notes |
|---|---|---|
| Father-in-law photo | `01`, `08` | Morgan has this. Full bleed, no text. Same photo both times, or a second one for `08`. |
| Check engine light | `02` unlit, and lit on every logo below | Amber. Simple SVG with the light as its own layer. The one asset the whole deck reuses. |
| Terminal glyph + light | `02`, `03`, `08` | Generic terminal, not a specific shell. |
| Python (+ npm, Go behind) + light | `02`, `04`, `08` | Python forward, the other two smaller. |
| Docker whale + light | `02`, `05`, `08` | |
| Sparkle or plug + light | `02`, `06`, `08` | Generic agent/MCP glyph, not a vendor logo. |
| xz wordmark + light | `07` | |
| VS Code logo + light | `07` | |

The four-logo composite is needed twice in `08`, lights on and lights
off, so the light layer must be renderable dark.

## To verify

- [ ] **VS Code extension compromise.** The abstract says it "breached
      GitHub itself." Need the source before the sentence in
      `07-take-stock.md` is written. Nothing goes in the mouth without it.
- [ ] **xz.** CVE-2024-3094, March 2024, liblzma, sshd via the systemd
      notification patch. One sentence.
- [ ] **`npx -y @scope/server`** with no version fetches latest.
- [ ] **Claude Code `/plugin install`** — does it record a marketplace
      commit? "The managed path exists" is the honest line either way.
- [ ] **Codex** has skill/plugin install and update.
- [x] **Language tooling claims** (`04`): `@latest`, npm lifecycle scripts,
      terraform state version, pip sdist vs wheel. Sources in the slide's
      backmatter. Install-hook example is Shai-Hulud or ua-parser-js, not
      event-stream.
- [x] **`mise`** installs via `curl https://mise.run | sh`. pyenv and nvm are
      the same shape. asdf is not (Go binary since 0.16); do not name it.
- [ ] **Father-in-law knows he's on a slide.**

## If it runs long

There's nothing to cut; the format is fixed. If a slide's narration runs
past 15 seconds in practice, trim the narration, not the slide. The
narration in each `Note:` is already at the budget; treat it as a ceiling.

## Conventions

Matches `nixos-handheld-talk` and `nix-k8s-talk`:

- Slide titles are flat descriptive labels, not jokes. Bits go in the
  speaker's mouth, not on the slide.
- No first person in slide text, except the label "Ours" on `02`. Commentary
  is voiceover.
- Speaker notes are the actual narration, in prose.
- Styling is inline per element. `index.html` carries heading sizes and the shared
  `.placeholder`, `.method`, and `.gaps` rules and nothing else.
- No fragments. Every slide is static; a concept that needs a reveal gets
  another slide.
- Each slide file ends in a backmatter comment block with scope notes,
  graphics needed, and things to verify.
- Goonco and any other former employer stay in the narration, not on
  the slide.
