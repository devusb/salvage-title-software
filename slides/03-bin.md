## Shell scripts

<div style="display: flex; align-items: center; gap: 1.5em;">
<div class="logo"><img class="mark" src="slides/logos/terminal.svg" /><img class="cel" src="slides/cel-on.svg" /></div>
<div class="code">
<p class="path">~/bin/deploy &nbsp;·&nbsp; pasted in #eng-tools</p>
<pre><code class="language-bash">#!/bin/bash
set -e
export AWS_PROFILE=prod
TAG=$(git rev-parse --short HEAD)
sed -i '' "s/__TAG__/$TAG/" k8s/deploy.yaml
kubectl --context prod apply -f k8s/deploy.yaml
aws s3 cp k8s/deploy.yaml s3://acme-tools/last.yaml</code></pre>
</div>
</div>

Note: This one's mine, I did it for years. Someone posts a shell script in Slack, you copy it to tilde-bin, it's on your PATH, now it's a command. Why not? It works, and anyone who reads bash can fix it.

---

## Shell scripts

<p class="eyebrow">Jank</p>

<ul class="gap">
<li>Bring your own dependencies</li>
<li>No version, no owner</li>
<li>Twelve lines. Forty of instructions</li>
</ul>

Note: Bring your own dependencies. Whatever it needs, jq, aws, a particular Python, you go find, and the Mac sed isn't the Linux sed. No version, no owner. The script is twelve lines. The message explaining how to run it is forty.

---

## Shell scripts

<p class="eyebrow">Risk</p>

<ul class="gap">
<li>Runs as you</li>
<li>No upstream to check against</li>
<li>In no inventory</li>
</ul>

Note: And it runs as you. On this laptop, you are the AWS keys, the kubeconfig, prod. There's no upstream to check your copy against; you have whatever was in the thread that day. And it's in no inventory anywhere.

<!--
============================================================
BACKMATTER / RAW NOTES
============================================================

Pattern 1 of 4. The skills risk slide ends on "it's the
shell script again."

GRAPHICS: done. Marks in slides/logos/, light is cel-on.svg /
cel-off.svg positioned over the mark by .logo CSS.
-->
