## Containers

<div style="display: flex; align-items: center; gap: 1.5em;">
<div class="logo"><img class="mark" src="slides/logos/docker.svg" /><img class="cel" src="slides/cel-on.svg" /></div>
<div class="code">
<p class="path">docker run &nbsp;·&nbsp; from my shell history</p>
<pre><code class="language-bash">aws ecr get-login-password | docker login --password-stdin $ECR
docker pull registry.internal/platform/vmware-build:latest
docker run --rm -it \
  -e AWS_ACCESS_KEY_ID -e AWS_SECRET_ACCESS_KEY \
  -v /var/run/docker.sock:/var/run/docker.sock \
  registry.internal/platform/vmware-build:latest</code></pre>
</div>
</div>

Note: Pattern three, the one that's supposed to be the fix. Everyone has one; I've had several. This one I pulled twelve times, at latest, with my AWS keys passed in and the docker socket mounted, because that's what made it work.

---

## Containers

<p class="eyebrow">Jank</p>

<ul class="gap">
<li>Built by hand, pushed to <code>:latest</code></li>
<li>On macOS, runs inside a Linux VM</li>
<li>Lost Dockerfile, nobody can rebuild</li>
</ul>

Note: Somebody built it by hand and pushed it to latest, so nobody knows which commit it is. On a Mac it runs in a Linux VM, so every build and every file sync pays for that. And the Dockerfile drifted, or it's gone.

---

## Containers

<p class="eyebrow">Risk</p>

<ul class="gap">
<li>Has your credentials, or it's useless</li>
<li>Pushed from a laptop</li>
<li>Least scrutiny, most access</li>
</ul>

Note: It has your credentials, or it can't deploy. In the cloud, they're on a machine that isn't yours. Prod gets scanned; this got pushed from a laptop. The image you look at least can reach the most.

<!--
============================================================
BACKMATTER / RAW NOTES
============================================================

PROTECT: the inversion line (least scrutiny, most access).

"Passing a scanner" in the narration calls back to the caption on 02.

GRAPHICS: done. Marks in slides/logos/, light is cel-on.svg /
cel-off.svg positioned over the mark by .logo CSS.
-->
