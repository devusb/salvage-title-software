## The Container

<div style="display: flex; align-items: center; gap: 1.5em;">
<div class="placeholder" style="width: 200px; height: 200px; flex: none;">
[GRAPHIC: Docker whale + light]
</div>
<div class="method" style="flex: 1;">
<p><code>devcontainer.json</code> → <code>registry.internal/devenv:latest</code>. Built once.</p>
<p class="why">The good version. Reproducible.</p>
</div>
</div>

Note: Pattern three, the one that's supposed to be the fix. A devcontainer pointing at an image in your registry. Somebody built it. And this is genuinely good. Reproducible, one-click onboarding. It fixes both of the last two slides.

---

## The Container

<p class="eyebrow">Jank</p>

<ul class="gap">
<li>Built by hand. Which commit?</li>
<li><code>:latest</code> moved</li>
<li>Dockerfile gone</li>
</ul>

Note: Somebody built it by hand, on their laptop, and pushed it. From what commit? Latest isn't yesterday's latest. The Dockerfile drifted, or it's gone. Nobody can rebuild it.

---

## The Container

<p class="eyebrow">Risk</p>

<ul class="gap">
<li>Prod: promoted. Dev: pushed from a laptop</li>
<li>Mounts <code>~/.aws</code></li>
<li>Least scrutiny, most access</li>
</ul>

Note: Here's the indictment. Your production image can't reach that registry without passing a scanner. Your dev image was docker push from a laptop. And it's the one with your credentials mounted in it. The image you look at least can reach the most.

<!--
============================================================
BACKMATTER / RAW NOTES
============================================================

PROTECT: the inversion line (least scrutiny, most access).

"Prod: promoted" calls back to the caption on 02.

GRAPHICS NEEDED:
  - Docker whale with the light.
-->
