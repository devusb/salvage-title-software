## The Container

<div style="display: flex; align-items: flex-start; gap: 1.2em;">
<div class="placeholder" style="width: 170px; height: 170px; flex: none;">
[GRAPHIC: Docker logo + check engine light]
</div>
<div style="flex: 1;">
<div class="mwg">
<p class="fragment"><strong>Method</strong> <code>.devcontainer/devcontainer.json</code> → <code>registry.internal/devenv:latest</code>. Or a wrapper in <code>~/bin</code> that does <code>docker run</code>. Someone built it. Once.</p>
<p class="fragment"><strong>Why</strong> This is the good version. Reproducible. One-click onboarding. It genuinely fixes the last two slides.</p>
</div>
<div class="gaps">
<div class="fragment">
<h4>Jank</h4>
<ul>
<li>Built by hand, pushed by hand. From which commit?</li>
<li><code>:latest</code> isn't yesterday's <code>:latest</code></li>
<li>The Dockerfile drifted from the image, or is gone</li>
<li>Base pinned the day it was built. Fourteen months ago</li>
</ul>
</div>
<div class="fragment">
<h4>Risk</h4>
<ul>
<li>The production image can't reach the registry without passing a scanner. The dev image was pushed from a laptop</li>
<li>No CI, no scan, no signature, no SBOM, no rebuild cadence</li>
<li>Prod runs least-privilege. Dev mounts <code>~/.aws</code>, the kubeconfig, the git token</li>
<li>The image with the least scrutiny has the most access</li>
</ul>
</div>
</div>
</div>
</div>

Note: Pattern three, and this is the one that's supposed to be the fix. Dev containers. A devcontainer.json pointing at an image in your registry, or a wrapper script that does docker run. Somebody built it. And this is genuinely good. It's reproducible, onboarding is one click, it fixes both of the last two slides. Here's the thing. Somebody built it by hand, on their laptop, and pushed it. From what commit? Latest isn't yesterday's latest. The Dockerfile drifted or it's gone. And here's the indictment. Your production image cannot reach that registry without going through a scanner. Chainguard base, Grype in CI, Wiz watching it land. Your dev image was docker push from a laptop. Same registry. Same artifact type. Different path. And it's the image with the credentials in it. Prod runs least-privilege. Dev mounts your AWS directory and your kubeconfig, because that's what made it work. The image you look at least can reach the most.

<!--
============================================================
BACKMATTER / RAW NOTES
============================================================

TIMING: ~0:40.

NARRATE: the indictment (same registry, different path) and
the inversion (least scrutiny, most access). The jank column
sits on screen; this room already knows it.

PROTECT: the inversion line if the slide runs long.

Calls back to 02-pivot.md's tool names. If those change,
change them here too.

GRAPHICS NEEDED:
  - Docker logo (the whale) with the check engine light on.
-->
