## Ecosystem tooling

<div style="display: flex; align-items: center; gap: 1.5em;">
<div class="logo cluster"><img class="minor a" src="slides/logos/npm.svg" /><img class="minor b" src="slides/logos/go.svg" /><img class="mark" src="slides/logos/python.svg" /><img class="cel" src="slides/cel-on.svg" /></div>
<div class="code">
<p class="path">README.md &nbsp;·&nbsp; Getting started</p>
<pre><code class="language-bash">brew install libpq openssl                # system libs
uv python install 3.12 &amp;&amp; uv sync         # python
source .venv/bin/activate
nvm install 20 &amp;&amp; nvm use 20              # node
npm ci
go mod download                           # go
direnv allow                              # glue</code></pre>
</div>
</div>

Note: Pattern two: language ecosystem tooling. uv, nvm, npm, go mod. A repo is rarely one language, so a working shell is a ritual per language: pick the version, activate, fetch the deps. Then something to glue it together.

---

## Ecosystem tooling

<p class="eyebrow">Jank</p>

<ul class="gap">
<li>Covers the language, not the machine</li>
<li>One activation ritual per language</li>
<li>Glued together by a README</li>
</ul>

Note: Each tool covers its language and stops at the edge. Every one is fine. It's the seams: three activation models in one shell, system libraries from brew, a README or direnv holding it together. Nothing owns the whole environment.

---

## Ecosystem tooling

<p class="eyebrow">Risk</p>

<ul class="gap">
<li>Lockfiles cover deps, not tools</li>
<li><code>direnv allow</code>: a script runs on every <code>cd</code></li>
<li>Dependabot watches the repo, not your tools</li>
</ul>

Note: The lockfiles cover the dependencies, not uv, nvm, brew, or direnv. The glue is a script in the repo that runs every time you cd in, as you. Dependabot watches the repo. Nothing watches the tools you installed.

<!--
============================================================
BACKMATTER / RAW NOTES
============================================================

The thesis of this pattern is the seams between language
tools: each covers its language, and the repo has three of
them plus system libs, so onboarding is a ritual per
language glued by a README or direnv. That is the mixed-
environment problem Flox solves; it stays unnamed. The
ecosystem tool manages the language and nothing beneath it,
so the real setup is an amalgam: venv plus apt plus brew
plus a README. That is the Flox-shaped hole. It stays
unnamed; the title slide says Flox and that is enough.

Jank slide is the heaviest in the deck at 17 words. If it
has to lose one, the third bullet goes to narration only.

No scripts on this slide: setup.sh is pattern one. The
Goonco venv-plus-scripts story blends the two patterns, so
it is out of this narration. Python leads; no Rust beyond the
cargo mention.

Terraform "which version" beat survives as "every laptop's
a different version." Sharper true version if there is ever
room: your clean plan upgraded the state and broke theirs.

VERIFIED (2026-09-11):
  - (no longer on the slide) go install pkg@latest ignores go.mod/go.sum
    entirely and resolves at install time. go.dev/ref/mod.
  - npm runs preinstall/install/postinstall by default,
    including for npm install -g. docs.npmjs.com/cli/v10/
    using-npm/scripts.
  - uv creates .venv by default; docs.astral.sh/uv/pip/
    environments shows `source .venv/bin/activate` as the
    activation command. `uv run` is the no-activate
    alternative; the slide shows activate on purpose.
  - uv:    curl -LsSf https://astral.sh/uv/install.sh | sh
    (screenshot astral.sh the week of the talk)
  - mise:  curl https://mise.run | sh
    pyenv: curl https://pyenv.run | bash
    nvm:   curl -o- .../install.sh | bash
    Do not name asdf; it is a Go binary since 0.16.
  - Terraform refuses state written by a newer version, and
    plan alone upgrades the snapshot. hashicorp/terraform
    #24271, #22649.
  - pip: sdists run the build backend (arbitrary code),
    wheels do not. Say "install hooks" not "pip runs code".
  - Shai-Hulud: Sept 2025, postinstall, 180+ packages, V2 in
    Nov hit 700+. ua-parser-js: Oct 2021, preinstall. NOT
    event-stream: its payload ran at require() time.

GRAPHICS: done. Marks in slides/logos/, light is cel-on.svg /
cel-off.svg positioned over the mark by .logo CSS.
-->
