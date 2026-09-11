## Language Tooling

<div style="display: flex; align-items: center; gap: 1.5em;">
<div class="placeholder" style="width: 200px; height: 200px; flex: none;">
[GRAPHIC: Python forward, npm + Go behind, light]
</div>
<div class="method" style="flex: 1;">
<p><code>venv</code> · <code>requirements.txt</code> · <code>./setup.sh</code> · <code>./seed.sh</code>. In that order.</p>
<p class="why">It's what the README says.</p>
</div>
</div>

Note: Pattern two. I worked somewhere the dev environment was a virtualenv and a pile of scripts you ran in a specific order, and if you got it wrong you started over. Why? It's what Python hands you. It's what the README says.

---

## Language Tooling

<div class="gaps">
<div>
<h4>Jank</h4>
<ul>
<li>Which version?</li>
<li>Version managers, via <code>curl | sh</code></li>
<li>Lockfile exists. Nobody uses it</li>
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

Note: Your plan is clean, theirs fails, the diff is a minor version. So we built version managers for the tools, and install those with curl pipe sh. At-latest means whoever owns the package tomorrow is on your machine tomorrow. Nothing is watching your laptop.

<!--
============================================================
BACKMATTER / RAW NOTES
============================================================

Goonco stays in the mouth. Python leads; no Rust.

GRAPHICS NEEDED:
  - Python logo forward, npm and Go smaller behind, light
    on the group.

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
    plan alone upgrades the snapshot. Your clean plan is
    what broke theirs. hashicorp/terraform #24271, #22649.
  - pip: sdists run the build backend (arbitrary code),
    wheels do not. Say "install hooks" not "pip runs code".

IF A NAME IS NEEDED for install-hook malware: Shai-Hulud
(Sept 2025, postinstall, 180+ packages, V2 in Nov hit 700+)
or ua-parser-js (Oct 2021, preinstall). NOT event-stream:
its payload ran at require() time, not on install.
-->
