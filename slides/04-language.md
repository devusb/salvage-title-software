## Ecosystem tooling

<div style="display: flex; align-items: center; gap: 1.5em;">
<div class="logo cluster"><img class="minor a" src="slides/logos/npm.svg" /><img class="minor b" src="slides/logos/go.svg" /><img class="mark" src="slides/logos/python.svg" /><img class="cel" src="slides/cel-on.svg" /></div>
<div class="code">
<p class="path">README.md &nbsp;·&nbsp; Getting started</p>
<pre><code class="language-bash">brew install libpq openssl                 # system libs
curl -LsSf https://astral.sh/uv/install.sh | sh
uv python install 3.12
uv sync
npm install -g @acme/cli                   # node
go install github.com/acme/tool@latest     # go</code></pre>
</div>
</div>

Note: Pattern two: language ecosystem tooling. uv, npm, cargo, go install, whatever your language hands you. It manages the language. A repo is rarely one language, so you usually have two or three of these, each with its own install story.

---

## Ecosystem tooling

<p class="eyebrow">Jank</p>

<ul class="gap">
<li>Covers the language, not the machine</li>
<li>Plus apt, brew, a README</li>
<li>One per language in the repo</li>
</ul>

Note: It covers the language, not the machine. uv is great, and libpq and openssl still come from brew, so setup is a README that starts with first, install these. And the package manager itself arrives by curl pipe sh.

---

## Ecosystem tooling

<p class="eyebrow">Risk</p>

<ul class="gap">
<li><code>@latest</code></li>
<li>Install hooks run code</li>
<li>Dependabot watches prod, not you</li>
</ul>

Note: At-latest: whoever owns the package tomorrow is on your machine tomorrow. Install hooks run code. Shai-Hulud was a postinstall script that stole npm tokens and republished itself. And Dependabot is watching the product repo. Nothing is watching your laptop.

<!--
============================================================
BACKMATTER / RAW NOTES
============================================================

The thesis of the jank slide is "not all-encompassing." The
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
  - go install pkg@latest ignores the local go.mod/go.sum
    entirely and resolves at install time. go.dev/ref/mod.
  - npm runs preinstall/install/postinstall by default,
    including for npm install -g. docs.npmjs.com/cli/v10/
    using-npm/scripts.
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
