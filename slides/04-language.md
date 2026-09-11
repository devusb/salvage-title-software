<!-- .slide: data-timing="15" -->
## Language Tooling

<div style="display: flex; align-items: center; gap: 1.5em;">
<div class="placeholder" style="width: 200px; height: 200px; flex: none;">
[GRAPHIC: Python logo forward, npm + Go behind, check engine light]
</div>
<div class="method" style="flex: 1;">
<p><code>venv</code>, <code>requirements.txt</code>, then <code>./setup.sh</code>, then <code>./seed.sh</code>, in that order. <code>npm i -g</code>. <code>go install …@latest</code>. Then pyenv, nvm, tfenv, mise, to manage the versions of the tools.</p>
<p class="why">It's what the language hands you. It's what the README says. And it does fix the last slide: the interpreter papers over the OS.</p>
</div>
</div>

Note: Pattern two. The language's own tooling. I worked at a shop where the dev environment was a Python virtualenv and then a pile of shell scripts you had to run in a specific order, and if you got the order wrong, you started over. Why do it that way? Because that's what Python hands you. That's what the README says. And honestly it fixes the last slide, the interpreter hides the OS from you.

---

<!-- .slide: data-timing="22" -->
## Language Tooling

<div class="gaps">
<div>
<h4>Jank</h4>
<ul>
<li>Which version. Your <code>terraform plan</code> is clean. Theirs fails</li>
<li>So: version managers for the tools. Installed with <code>curl | sh</code></li>
<li>Every ecosystem has a lockfile. Every team routes around it</li>
</ul>
</div>
<div>
<h4>Risk</h4>
<ul>
<li><code>@latest</code>. Whoever owns the package tomorrow is on your machine tomorrow</li>
<li><code>pip install</code> and <code>postinstall</code> run arbitrary code at install time</li>
<li>Dependabot watches the product repo. Nothing watches your laptop</li>
</ul>
</div>
</div>

Note: The jank is which version. Your terraform plan is clean and theirs fails and the diff is a minor version. So we invented version managers for the tools, pyenv, nvm, tfenv, mise, and each person installs those with curl pipe sh. That's slide one again, one level up. And every ecosystem has a lockfile, and every team has found a way around it. The risk. At-latest means whoever owns that package tomorrow is on your machine tomorrow. Install hooks run arbitrary code. And Dependabot is watching the product repo. Nothing is watching your laptop.

<!--
============================================================
BACKMATTER / RAW NOTES
============================================================

TIMING: 0:15 + 0:25.

Goonco stays in the mouth, not on the slide. Python leads;
no Rust, cargo install --locked isn't a line Morgan can
defend firsthand.

Cut from the jank column to fit three: stale lockfile from
2021, real environment is someone's laptop, committed
.venv/. Committed .venv/ is a one-word laugh if there's a
gap in the narration.

GRAPHICS NEEDED:
  - Python logo in front, npm and Go smaller behind, check
    engine light on the group.

VERIFY:
  - mise install one-liner is `curl https://mise.run | sh`
  - npm postinstall as the vector: event-stream (2018),
    ua-parser-js (2021). Pick one if a name is needed.
-->
