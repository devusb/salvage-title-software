## Containers

<div style="display: flex; align-items: center; gap: 1.5em;">
<div class="logo"><img class="mark" src="slides/logos/docker.svg" /><img class="cel" src="slides/cel-on.svg" /></div>
<div class="code">
<p class="path">Dockerfile</p>
<pre><code class="language-dockerfile">FROM ubuntu:latest
RUN apt-get update &amp;&amp; apt-get install -y \
      build-essential git curl jq \
      python3-pip nodejs npm
RUN curl -fsSL https://sh.rustup.rs | sh -s -- -y
RUN pip install -r requirements.txt
RUN npm install -g @acme/devtools</code></pre>
</div>
</div>

Note: Pattern three, the one that's supposed to be the fix. Everyone has one; I've had several. From ubuntu latest, apt-get everything, curl pipe sh, pip, npm. The last two slides, baked into one image. And it's genuinely good.

---

## Containers

<p class="eyebrow">Jank</p>

<ul class="gap">
<li>Built by hand, pushed to <code>:latest</code></li>
<li>On macOS, runs inside a Linux VM</li>
<li>Lost Dockerfile</li>
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
