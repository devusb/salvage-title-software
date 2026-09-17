## Containers

<div style="display: flex; align-items: center; gap: 1.5em;">
<div class="logo"><img class="mark" src="slides/logos/docker.svg" /><img class="cel" src="slides/cel-on.svg" /></div>
<div class="method" style="flex: 1;">
<p><code>devcontainer.json</code> → <code>registry.internal/devenv:latest</code>. Built once.</p>
</div>
</div>

Note: Pattern three, the one that's supposed to be the fix. A devcontainer pointing at an image in your registry. Somebody built it. And this is genuinely good. Reproducible, one-click onboarding. It fixes both of the last two slides.

---

## Containers

<p class="eyebrow">Jank</p>

<ul class="gap">
<li>Built by hand, pushed to <code>:latest</code></li>
<li>On macOS, runs inside a Linux VM</li>
<li>Dockerfile gone</li>
</ul>

Note: Somebody built it by hand and pushed it to latest, so nobody knows which commit it is. On a Mac it runs in a Linux VM, so every build and every file sync pays for that. And the Dockerfile drifted, or it's gone.

---

## Containers

<p class="eyebrow">Risk</p>

<ul class="gap">
<li>Prod: promoted. Dev: pushed from a laptop</li>
<li>Mounts <code>~</code>. Credentials included</li>
<li>Least scrutiny, most access</li>
</ul>

Note: Here's the indictment. Your production image can't reach that registry without passing a scanner. Your dev image was docker push from a laptop. And it mounts your whole home directory, credentials included. The image you look at least can reach the most.

<!--
============================================================
BACKMATTER / RAW NOTES
============================================================

PROTECT: the inversion line (least scrutiny, most access).

"Prod: promoted" calls back to the caption on 02.

GRAPHICS: done. Marks in slides/logos/, light is cel-on.svg /
cel-off.svg positioned over the mark by .logo CSS.
-->
