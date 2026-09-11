<!-- .slide: data-timing="15" -->
## The `~/bin` Script

<div style="display: flex; align-items: center; gap: 1.5em;">
<div class="placeholder" style="width: 200px; height: 200px; flex: none;">
[GRAPHIC: terminal logo + check engine light]
</div>
<div class="method" style="flex: 1;">
<p>Someone posts it in Slack. You copy it to <code>~/bin</code>. <code>~/bin</code> is on your PATH. You run it. For years.</p>
<p class="why">It works. Ten seconds to share. Anyone who reads bash can fix it. Nobody has to approve anything.</p>
</div>
</div>

Note: This first one is mine. I did this for years. Somebody posts a shell script in Slack, you copy it into tilde-bin, tilde-bin is on your PATH, and now it's a command. And why not? It works. It takes ten seconds to share and anybody who can read bash can fix it. Nobody has to approve anything. That's a real reason.

---

<!-- .slide: data-timing="22" -->
## The `~/bin` Script

<div class="gaps">
<div>
<h4>Jank</h4>
<ul>
<li>Assumes the tools the author had: <code>jq</code>, <code>yq</code>, <code>aws</code>, a particular Python</li>
<li><code>sed -i</code> vs <code>sed -i ''</code>. BSD vs GNU everything</li>
<li>The script is twelve lines. The message explaining it is forty</li>
</ul>
</div>
<div>
<h4>Risk</h4>
<ul>
<li>Runs as you. On this laptop, "you" is the AWS creds, the kubeconfig, the SSH agent. Prod</li>
<li>No integrity. Anyone in the channel could have posted "the fix"</li>
<li>Not in any inventory. Your SBOM doesn't know <code>~/bin</code> exists</li>
</ul>
</div>
</div>

Note: Here's the jank. It assumes you have whatever the author had. jq, yq, some Python. And even when you have them, they're the wrong flavor, because sed on a Mac is not sed on Linux. Which is why the script is twelve lines and the Slack message explaining how to run it is forty. And the risk. It runs as you. On a DevOps engineer's laptop, "you" is the AWS credentials and the kubeconfig and the SSH agent. It's prod. Anyone in that channel could have posted the fix. And it's in no inventory anywhere.

<!--
============================================================
BACKMATTER / RAW NOTES
============================================================

TIMING: 0:15 + 0:25.

Cut from the jank column to fit three: no version (drift),
no owner. Both survive in the mouth if there's time.

GRAPHICS NEEDED:
  - terminal/shell logo with the check engine light on it.
    Generic terminal glyph, not a specific shell's logo.

This is pattern 1 of 4. 06-skills.md ends on a bookend
slide, "it's the ~/bin script again," with this logo next
to the skills one.
-->
