## Containers

<div style="display: flex; align-items: center; gap: 1.5em;">
<div class="logo"><img class="mark" src="slides/logos/docker.svg" /><img class="cel" src="slides/cel-on.svg" /></div>
<pre style="flex: 1; width: auto; margin: 0; box-shadow: none;"><code class="language-dockerfile" style="font-size: 0.5em; line-height: 1.45; padding: 0.8em 1em;">FROM ubuntu:latest
RUN apt-get update &amp;&amp; apt-get install -y \
      build-essential git curl jq \
      python3-pip nodejs npm
RUN curl -fsSL https://sh.rustup.rs | sh -s -- -y
RUN pip install -r requirements.txt
RUN npm install -g @acme/devtools
RUN curl -fsSL https://mise.run | sh</code></pre>
</div>

Note: Pattern three, the one that's supposed to be the fix. Here's the Dockerfile. From ubuntu latest, apt-get everything, curl pipe sh, pip, npm. The last two slides, baked into one image. And this is genuinely good. Reproducible, one-click onboarding.

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
