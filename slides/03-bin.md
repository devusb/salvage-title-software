## The `~/bin` Script

<div style="display: flex; align-items: flex-start; gap: 1.2em;">
<div class="placeholder" style="width: 170px; height: 170px; flex: none;">
[GRAPHIC: terminal logo + check engine light]
</div>
<div style="flex: 1;">
<div class="mwg">
<p class="fragment"><strong>Method</strong> Someone posts it in Slack. You copy it to <code>~/bin</code>. <code>~/bin</code> is on your PATH. You run it. For years.</p>
<p class="fragment"><strong>Why</strong> It works. Ten seconds to share. Anyone who reads bash can fix it. Nobody has to approve anything.</p>
</div>
<div class="gaps">
<div class="fragment">
<h4>Jank</h4>
<ul>
<li>Assumes the tools the author had: <code>jq</code>, <code>yq</code>, <code>aws</code>, a particular Python</li>
<li><code>sed -i</code> vs <code>sed -i ''</code>. BSD vs GNU everything</li>
<li>The script is twelve lines. The message explaining it is forty</li>
<li>No version. Yours and theirs drift</li>
<li>No owner. Six months on, nobody knows who wrote it</li>
</ul>
</div>
<div class="fragment">
<h4>Risk</h4>
<ul>
<li>Runs as you. On this laptop, "you" is the AWS creds, the kubeconfig, the SSH agent, prod</li>
<li>No integrity. Anyone in the channel could have posted "the fix"</li>
<li>Not in any inventory. Your SBOM doesn't know <code>~/bin</code> exists</li>
</ul>
</div>
</div>
</div>
</div>

Note: This first one is mine. I did this for years. Somebody posts a shell script in Slack, you copy it into tilde-bin, tilde-bin's on your PATH, and now it's a command. Why? Because it works. It takes ten seconds to share and anybody who can read bash can fix it. That's a good reason. Here's the jank. It assumes you have whatever the author had, jq, yq, some Python. And even when you have them, they're the wrong flavor, because sed on a Mac is not sed on Linux. Which is why the script is twelve lines and the Slack message explaining how to run it is forty. And the risk. It runs as you. And on a DevOps engineer's laptop, "you" is the AWS credentials and the kubeconfig and the SSH agent. It's prod. And it's in no inventory anywhere.

<!--
============================================================
BACKMATTER / RAW NOTES
============================================================

TIMING: ~0:40.

NARRATE: deps -> mac/linux -> forty lines (they chain), then
"runs as you." Version, owner, integrity, inventory sit on
screen unspoken.

GRAPHICS NEEDED:
  - terminal/shell logo with the check engine light on it.
    Generic terminal glyph, not a specific shell's logo.

This is pattern 1 of 4. 06-skills.md ends with "it's the
~/bin script again," so the shape of this slide has to be
memorable enough to call back to.
-->
