## Language Ecosystem Tooling

<div style="display: flex; align-items: center; gap: 1.5em;">
<div class="placeholder" style="width: 200px; height: 200px; flex: none;">
[GRAPHIC: Python forward, npm + Go behind, light]
</div>
<div class="method" style="flex: 1;">
<p><code>pip</code> · <code>venv</code> · <code>npm</code> · <code>nvm</code> · <code>cargo</code> · <code>go install</code></p>
<p class="why">It's what the language hands you.</p>
</div>
</div>

Note: Pattern two: language ecosystem tooling. pip, virtualenvs, npm, nvm, cargo, whatever your language hands you. I worked somewhere the dev environment was a virtualenv and a stack of scripts you ran in order. Get the order wrong, start over.

---

## Language Ecosystem Tooling

<div class="gaps">
<div>
<h4>Jank</h4>
<ul>
<li>Covers the language. Not the machine</li>
<li>Plus fifty apt packages, twenty from brew, and a README</li>
<li>A package manager for the package manager</li>
</ul>
</div>
<div>
<h4>Risk</h4>
<ul>
<li><code>@latest</code></li>
<li>Install hooks run code</li>
<li>Dependabot watches prod, not you</li>
</ul>
</div>
</div>

Note: It covers the language, not the machine. You still need libpq, a compiler, twenty things from brew, so setup is a README: first, install these. Every laptop's a different version, so: a version manager for the package manager, via curl pipe sh.

<!--
============================================================
BACKMATTER / RAW NOTES
============================================================

The thesis of this slide is "not all-encompassing." The
ecosystem tool manages the language and nothing beneath it,
so the real setup is an amalgam: venv plus apt plus brew
plus a README. That is the Flox-shaped hole. It stays
unnamed; the intro slide says Flox and that is enough.

Goonco stays in the mouth. Python leads; no Rust beyond the
cargo mention in the examples line.

Risk column is on screen only on this slide. Narration is
all jank; 06-skills.md carries the risk beat.

Terraform "which version" beat survives as "every laptop's
a different version." Sharper true version if there is ever
room: your clean plan upgraded the state and broke theirs.

VERIFIED (2026-09-11):
  - go install pkg@latest ignores the local go.mod/go.sum
    entirely and resolves at install time. go.dev/ref/mod.
  - npm runs preinstall/install/postinstall by default,
    including for npm install -g. docs.npmjs.com/cli/v10/
    using-npm/scripts.
  - mise:  curl https://mise.run | sh
    pyenv: curl https://pyenv.run | bash
    nvm:   curl -o- .../install.sh | bash
    Do not name asdf; it is a Go binary since 0.16.
  - Terraform refuses state written by a newer version, and
    plan alone upgrades the snapshot. hashicorp/terraform
    #24271, #22649.
  - pip: sdists run the build backend (arbitrary code),
    wheels do not. Say "install hooks" not "pip runs code".

IF A NAME IS NEEDED for install-hook malware: Shai-Hulud
(Sept 2025, postinstall, 180+ packages, V2 in Nov hit 700+)
or ua-parser-js (Oct 2021, preinstall). NOT event-stream:
its payload ran at require() time, not on install.

GRAPHICS NEEDED:
  - Python logo forward, npm and Go smaller behind, light
    on the group.
-->
