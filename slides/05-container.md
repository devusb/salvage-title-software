<!-- .slide: data-timing="15" -->
## The Container

<div style="display: flex; align-items: center; gap: 1.5em;">
<div class="placeholder" style="width: 200px; height: 200px; flex: none;">
[GRAPHIC: Docker logo + check engine light]
</div>
<div class="method" style="flex: 1;">
<p><code>.devcontainer/devcontainer.json</code> → <code>registry.internal/devenv:latest</code>. Or a wrapper in <code>~/bin</code> that does <code>docker run</code>. Someone built it. Once.</p>
<p class="why">This is the good version. Reproducible. One-click onboarding. It genuinely fixes the last two slides.</p>
</div>
</div>

Note: Pattern three, and this is the one that's supposed to be the fix. Dev containers. A devcontainer.json pointing at an image in your registry, or a wrapper script that does docker run. Somebody built it. And this is genuinely good. It's reproducible, onboarding is one click, it fixes both of the last two slides.

---

<!-- .slide: data-timing="22" -->
## The Container

<div class="gaps">
<div>
<h4>Jank</h4>
<ul>
<li>Built by hand, pushed by hand. From which commit?</li>
<li><code>:latest</code> isn't yesterday's <code>:latest</code></li>
<li>The Dockerfile drifted from the image. Or is gone</li>
</ul>
</div>
<div>
<h4>Risk</h4>
<ul>
<li>The production image can't reach the registry without passing a scanner. The dev image was pushed from a laptop</li>
<li>Prod runs least-privilege. Dev mounts <code>~/.aws</code>, the kubeconfig, the git token</li>
<li>The image with the least scrutiny has the most access</li>
</ul>
</div>
</div>

Note: Here's the thing. Somebody built it by hand, on their laptop, and pushed it. From what commit? Latest isn't yesterday's latest. The Dockerfile drifted, or it's gone. And here's the indictment. Your production image cannot reach that registry without going through a scanner. Chainguard base, Grype in CI, Wiz watching it land. Your dev image was docker push from a laptop. Same registry. Same artifact type. Different path. And it's the image with the credentials in it. Prod runs least-privilege. Dev mounts your AWS directory and your kubeconfig, because that's what made it work. The image you look at least can reach the most.

<!--
============================================================
BACKMATTER / RAW NOTES
============================================================

TIMING: 0:15 + 0:25.

PROTECT: the inversion line (least scrutiny, most access)
if the slide runs long.

Calls back to 02-pivot.md's tool names. If those change,
change them here too.

GRAPHICS NEEDED:
  - Docker whale with the check engine light on.
-->
