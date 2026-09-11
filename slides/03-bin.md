## The `~/bin` Script

<div style="display: flex; align-items: center; gap: 1.5em;">
<div class="placeholder" style="width: 200px; height: 200px; flex: none;">
[GRAPHIC: terminal + light]
</div>
<div class="method" style="flex: 1;">
<p>Slack → <code>~/bin</code> → PATH. For years.</p>
<p class="why">It works. Anyone can fix it.</p>
</div>
</div>

Note: This one's mine, I did it for years. Someone posts a shell script in Slack, you copy it to tilde-bin, it's on your PATH, now it's a command. Why not? It works, and anyone who reads bash can fix it.

---

## The `~/bin` Script

<div class="gaps">
<div>
<h4>Jank</h4>
<ul>
<li>Author's tools assumed</li>
<li>BSD vs GNU</li>
<li>12 lines of script, 40 of instructions</li>
</ul>
</div>
<div>
<h4>Risk</h4>
<ul>
<li>Runs as you</li>
<li>Anyone could post "the fix"</li>
<li>In no inventory</li>
</ul>
</div>
</div>

Note: It assumes whatever the author had installed. Then sed on a Mac isn't sed on Linux, so the script is twelve lines and the message explaining it is forty. And it runs as you. On this laptop, you are the AWS keys, the kubeconfig, prod.

<!--
============================================================
BACKMATTER / RAW NOTES
============================================================

Pattern 1 of 4. 06-skills.md ends on a bookend slide with
this logo next to the skills one.

GRAPHICS NEEDED:
  - terminal glyph with the check engine light. Generic,
    not a specific shell's logo.
-->
