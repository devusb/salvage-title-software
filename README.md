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
| `01-father-in-law.md` | 2 | The photo, the check engine light |
| `02-pivot.md` | 2 | How you ship to customers, how you ship to yourself |
| `03-bin.md` | 2 | Pattern 1: the `~/bin` script |
| `04-language.md` | 2 | Pattern 2: language tooling |
| `05-container.md` | 2 | Pattern 3: the container |
| `06-skills.md` | 3 | Pattern 4: skills and MCP, then the bookend |
| `07-take-stock.md` | 2 | xz, VS Code |
| `08-close.md` | 4 | Lights on, lights off, our version, thanks |

Every pattern gets two slides: logo with the check engine light plus how
it's done and why, then **Jank** | **Risk** at three short bullets each.
The why is always a real reason. Jank is what's broken. Risk is what's
exposed.

Pattern 1 and pattern 4 are the same pattern; `06-skills.md` ends on a
bookend slide, "it's the `~/bin` script again."

## Word budget

Fifteen seconds is about 40 spoken words and about 3 seconds of reading.

- On screen: a title and at most ~15 words. Gaps slides are six bullets of
  two to six words.
- Narration: at most ~40 words per slide. The slide leaves without you.
- Anything cut from a slide that still matters goes in the narration, and
  anything cut from the narration is gone.

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
- [ ] **`mise`** installs via `curl https://mise.run | sh`.
- [ ] **Chainguard / Grype / Wiz / SentinelOne** — swap for whatever the
      room actually uses if the venue is known. They appear in `02`, `05`,
      and `06` together.
- [ ] **Father-in-law knows he's on a slide.**

## If it runs long

There's nothing to cut; the format is fixed. If a slide's narration runs
past 15 seconds in practice, trim the narration, not the slide. The
narration in each `Note:` is already at the budget; treat it as a ceiling.

## Conventions

Matches `nixos-handheld-talk` and `nix-k8s-talk`:

- Slide titles are flat descriptive labels, not jokes. Bits go in the
  speaker's mouth, not on the slide.
- No first person in slide text. Commentary is voiceover.
- Speaker notes are the actual narration, in prose.
- Styling is inline per element. `index.html` carries the shared
  `.placeholder`, `.method`, and `.gaps` rules and nothing else.
- No fragments. Every slide is static; a concept that needs a reveal gets
  another slide.
- Each slide file ends in a backmatter comment block with scope notes,
  graphics needed, and things to verify.
- Goonco and any other former employer stay in the narration, not on
  the slide.
