# Salvage Title Software

**How we ship to ourselves** — lightning talk, 5 minutes.

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
that goes green / yellow / red against each slide's budget). `Esc` for the
overview.

## Practicing

```
http://localhost:3000/?practice
```

Auto-advances every slide on its budget and plays a short tick on each
advance. `P` pauses and resumes (red outline while paused). Open the
speaker view alongside for the clock. Without `?practice` nothing ever
advances on its own.

## Structure

20 slides, all static. No fragments.

| File | Section | Budget |
|---|---|---|
| `00-title.md` | Title, speaker intro | 0:15 |
| `01-father-in-law.md` | The photo, the check engine light | 0:32 |
| `02-pivot.md` | How you ship to customers, how you ship to yourself | 0:20 |
| `03-bin.md` | Pattern 1: the `~/bin` script (method, gaps) | 0:37 |
| `04-language.md` | Pattern 2: language tooling (method, gaps) | 0:37 |
| `05-container.md` | Pattern 3: the container (method, gaps) | 0:37 |
| `06-skills.md` | Pattern 4: skills and MCP (method, gaps, bookend) | 0:41 |
| `07-take-stock.md` | xz, VS Code, the question | 0:20 |
| `08-close.md` | Lights on, lights off, our version, thanks | 0:37 |

Planned 4:36 against a 5:00 slot. Roughly 14 seconds a slide. Budgets are
the `data-timing` on each slide; the table is derived from them.

Every pattern gets two slides: logo with the check engine light plus
**Method** and **Why**, then **Jank** | **Risk** at three bullets each. The Why is always a real
reason. The Jank is what's broken. The Risk is what's exposed.

Pattern 1 and pattern 4 are the same pattern; `06-skills.md` ends on a bookend slide,
"it's the `~/bin` script again."

## Graphics to make

Every slot is marked in the slides with a dashed `.placeholder` box that
says what goes there. None exist yet.

| Graphic | Used in | Notes |
|---|---|---|
| Father-in-law photo | `01`, `08` | Morgan has this. Full bleed, no text. |
| Check engine light | `01`, and on every logo below | Amber, lit. Simple SVG. The one asset the whole deck reuses. |
| Terminal glyph + light | `02`, `03`, `06`, `08` | Generic terminal, not a specific shell. |
| Python (+ npm, Go behind) + light | `02`, `04`, `08` | Python forward, the other two smaller. |
| Docker whale + light | `02`, `05`, `08` | |
| Sparkle or plug + light | `02`, `06`, `08` | Generic agent/MCP glyph, not a vendor logo. |
| xz wordmark + light | `07` | |
| VS Code logo + light | `07` | |

For `08-close.md` the four-logo composite is needed twice, lights on and
lights off, so the light layer must be renderable dark.

## To verify

- [ ] **VS Code extension compromise.** The abstract says it "breached
      GitHub itself." Need the source before the sentence in
      `07-take-stock.md` is written. Nothing goes in the mouth without it.
- [ ] **xz.** CVE-2024-3094, March 2024, liblzma, sshd via the systemd
      notification patch. One sentence.
- [ ] **`npx -y @scope/server`** with no version fetches latest. Check how
      npx caches so "every cold start" is precise.
- [ ] **Claude Code `/plugin install`** — does it record a marketplace
      commit? If so, "the default path doesn't pin" is the honest line and
      is already what the slide says.
- [ ] **Codex** has skill/plugin install and update, so "Claude Code and
      Codex" is accurate.
- [ ] **`mise`** installs via `curl https://mise.run | sh`.
- [ ] **Chainguard / Grype / Wiz / SentinelOne** — swap for whatever the
      room actually uses if the venue is known. They appear in `02`, `05`,
      and `06` together.
- [ ] **Father-in-law knows he's on a slide.**

## Cuts, if it runs long

Decided in advance, in order:

1. `07-take-stock.md` — fold the xz and VS Code sentences into the top
   of `08-close.md`, drop the slide
2. `04-language.md` — Jank column becomes one spoken sentence
3. `06-skills.md` — drop the bookend slide, say the line over the gaps slide
4. `08-close.md` — drop the photo reprise, end on "take inventory"

Protect the photo open, the container inversion line, the `~/bin`
bookend, and the lights-on / lights-off pair.

## Conventions

Matches `nixos-handheld-talk` and `nix-k8s-talk`:

- Slide titles are flat descriptive labels, not jokes. Bits go in the
  speaker's mouth, not on the slide.
- No first person in slide text. Commentary is voiceover.
- Speaker notes are the actual narration, in prose.
- Styling is inline per element. `index.html` carries the shared
  `.placeholder`, `.gaps`, and `.mwg` rules and nothing else.
- No fragments. Every slide is static; a concept that needs a reveal gets another slide.
- Each slide file ends in a backmatter comment block with scope notes,
  cut candidates, graphics needed, and things to verify.
- Goonco and any other former employer stay in the narration, not on
  the slide.
