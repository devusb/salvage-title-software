## Language Tooling

<div style="display: flex; align-items: flex-start; gap: 1.2em;">
<div class="placeholder" style="width: 170px; height: 170px; flex: none;">
[GRAPHIC: Python logo forward, npm + Go behind, check engine light]
</div>
<div style="flex: 1;">
<div class="mwg">
<p class="fragment"><strong>Method</strong> <code>venv</code>, <code>requirements.txt</code>, then <code>./setup.sh</code>, then <code>./seed.sh</code>, in that order. <code>npm i -g</code>. <code>go install …@latest</code>. Then pyenv, nvm, tfenv, mise, to manage the versions of the tools.</p>
<p class="fragment"><strong>Why</strong> It's what the language hands you. It's what the README says. And it does fix the last slide: the interpreter papers over the OS.</p>
</div>
<div class="gaps">
<div class="fragment">
<h4>Jank</h4>
<ul>
<li>Which version. Your <code>terraform plan</code> is clean. Theirs fails</li>
<li>Version managers for the tools, installed with <code>curl | sh</code></li>
<li>Every ecosystem has a lockfile. Every team routes around it</li>
<li>The one that exists is from 2021 and doesn't resolve</li>
<li>The real environment is someone's laptop</li>
<li>Someone committed <code>.venv/</code></li>
</ul>
</div>
<div class="fragment">
<h4>Risk</h4>
<ul>
<li><code>@latest</code>: whoever owns the package tomorrow is on your machine tomorrow</li>
<li><code>pip install</code> and <code>postinstall</code> run arbitrary code at install time</li>
<li>Dependabot watches the product repo, not your laptop</li>
<li>N ecosystems, N supply chains, zero CVE feeds for the internal tool</li>
</ul>
</div>
</div>
</div>
</div>

Note: Pattern two. The language's own tooling. I worked at a shop where the dev environment was a Python virtualenv and then a pile of shell scripts you had to run in a specific order, and if you got the order wrong, you started over. Why do it that way? Because that's what Python hands you. That's what the README says. And honestly it fixes the last slide, the interpreter hides the OS. The jank is which version. Your terraform plan is clean and theirs fails and the diff is a minor version. So we invented version managers for the tools, pyenv, nvm, tfenv, mise, and each person installs those with curl pipe sh. That's slide one again, one level up. And every ecosystem has a lockfile, and every team has found a way around it. Risk. At-latest means whoever owns that package tomorrow is on your machine tomorrow. Install hooks run arbitrary code. And Dependabot is watching the product repo. Nothing is watching your laptop.

<!--
============================================================
BACKMATTER / RAW NOTES
============================================================

TIMING: ~0:40.

NARRATE: the venv-and-scripts onboarding story (Goonco stays
in the mouth, not on the slide), "which terraform," the
version-managers-are-pattern-1 callback, then @latest and
Dependabot. Lockfile and .venv/ sit on screen.

Python leads. No Rust on this slide; cargo install --locked
is a good line but not one Morgan can defend firsthand.

GRAPHICS NEEDED:
  - Python logo in front, npm and Go logos smaller behind,
    check engine light on the group.

VERIFY:
  - mise install one-liner is `curl https://mise.run | sh`
  - npm postinstall as the vector: event-stream (2018),
    ua-parser-js (2021). Pick one if a name is needed.
-->
