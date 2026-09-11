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

<p class="eyebrow">Jank</p>

<ul class="gap">
<li>Author's tools assumed</li>
<li>BSD vs GNU</li>
<li>Twelve lines. Forty of instructions</li>
</ul>

Note: It assumes whatever the author had installed. Then sed on a Mac isn't sed on Linux. So the script is twelve lines, and the Slack message explaining how to run it is forty.

---

## The `~/bin` Script

<p class="eyebrow">Risk</p>

<ul class="gap">
<li>Runs as you</li>
<li>Anyone could post "the fix"</li>
<li>In no inventory</li>
</ul>

Note: And it runs as you. On this laptop, you are the AWS keys, the kubeconfig, prod. Anyone in that channel could have posted the fix. And it's in no inventory anywhere. Your SBOM doesn't know tilde-bin exists.

<!--
============================================================
BACKMATTER / RAW NOTES
============================================================

Pattern 1 of 4. The skills risk slide ends on "it's the
~/bin script again."

GRAPHICS NEEDED:
  - terminal glyph with the check engine light. Generic,
    not a specific shell's logo.
-->
