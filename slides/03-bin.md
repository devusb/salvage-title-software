## Shell scripts

<div style="display: flex; align-items: center; gap: 1.5em;">
<div class="logo"><img class="mark" src="slides/logos/terminal.svg" /><img class="cel" src="slides/cel-on.svg" /></div>
<div class="code">
<p class="path">~/bin &nbsp;·&nbsp; from my shell history</p>
<pre><code class="language-bash">mkdir ~/bin &amp;&amp; export PATH=$PATH:~/bin
wget https://storage.googleapis.com/…/gke-gcloud-auth-plugin.tar.gz
tar xf … &amp;&amp; mv gke-gcloud-auth-plugin ~/bin/
curl https://vendor-templates.s3.amazonaws.com/eks/install-otel.sh | bash -s
curl http://build-box:3000/build/200/reproduce | bash</code></pre>
</div>
</div>

Note: This one's mine. Some of it is from the Before Time, some from last month. A PATH hack, a binary untarred into tilde-bin, a script from a bucket piped to bash, curl pipe bash from the one build box. It works.

---

## Shell scripts

<p class="eyebrow">Jank</p>

<ul class="gap">
<li>Bring your own dependencies</li>
<li>No version, no owner</li>
<li>Four install methods, one directory</li>
</ul>

Note: Four ways to install things into one directory. The plugin needs gcloud, the script needs an EKS context, you go find those. No version, no owner: that tarball was four-oh-one once and stayed four-oh-one until I deleted it.

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
