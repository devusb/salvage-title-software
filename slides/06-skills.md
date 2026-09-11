<!-- .slide: data-timing="15" -->
## Skills and MCP

<div style="display: flex; align-items: center; gap: 1.5em;">
<div class="placeholder" style="width: 200px; height: 200px; flex: none;">
[GRAPHIC: sparkle or plug icon + check engine light]
</div>
<div class="method" style="flex: 1;">
<p>Copy a <code>SKILL.md</code> into <code>~/.claude/skills/</code>. Clone a repo of them. <code>npx -y @scope/server</code> in a JSON file. Claude Code and Codex have plugin systems now: marketplaces, install, update.</p>
<p class="why">Brand new. Enormous, immediate value. Everyone's sharing. This is the Slack script in 2015, and that was good energy.</p>
</div>
</div>

Note: Pattern four. Skills and MCP servers. You copy a SKILL.md into a directory. You clone somebody's repo of them. You put npx dash y some-package in a JSON file. And to be fair, Claude Code and Codex both have plugin systems now, with marketplaces and install and update commands, which is more than tilde-bin ever had. Why? Because it's brand new and the value is enormous and everyone is sharing. This is exactly the Slack script in 2015, and that was good energy. This is how tooling ecosystems get built.

---

<!-- .slide: data-timing="18" -->
## Skills and MCP

<div class="gaps">
<div>
<h4>Jank</h4>
<ul>
<li>The managed path exists. Most of what's on your disk didn't come through it</li>
<li>Clone at HEAD. Copied file. <code>npx -y</code> at latest</li>
<li>Review is reading markdown for the one line that says fetch-and-run</li>
</ul>
</div>
<div>
<h4>Risk</h4>
<ul>
<li>Runs as you. And "you" is now an agent with your credentials that does what the file says</li>
<li>A malicious skill doesn't need a payload. It needs a sentence</li>
<li>Nothing in your stack sees this layer. No Grype for <code>~/.claude</code>. Wiz doesn't know the directory exists. SentinelOne is looking for a binary</li>
</ul>
</div>
</div>

Note: The jank: the managed path exists, and most of what's on your disk didn't come through it. Review means reading a markdown file looking for the one line that says fetch and run. The risk: it runs as you, except now "you" is an agent holding your credentials that does what the file says. A malicious skill doesn't need a payload. It needs a sentence. And nothing in your security stack sees this layer. Wiz doesn't know the directory exists. SentinelOne is looking for a binary, and the threat is a paragraph.

---

<!-- .slide: data-timing="8" -->
<div style="display: flex; gap: 3em; justify-content: center; align-items: center; margin-bottom: 0.6em;">
<div class="placeholder" style="width: 200px; height: 200px;">
[GRAPHIC: terminal logo + light]
</div>
<div class="placeholder" style="width: 200px; height: 200px;">
[GRAPHIC: sparkle/plug + light]
</div>
</div>

### It's the `~/bin` script again.

Note: It's the tilde-bin script again. Prose you found on the internet, copied into a directory the tool searches, run as you.

<!--
============================================================
BACKMATTER / RAW NOTES
============================================================

TIMING: 0:15 + 0:20 + 0:10.

The bookend gets its own slide. Land the line and stop.
Next slide is the quiet one.

GRAPHICS NEEDED:
  - sparkle (agent) or plug (MCP) glyph with the check
    engine light. Generic, not a vendor logo.
  - bookend slide reuses the terminal and sparkle
    composites side by side.

VERIFY:
  - `npx -y @scope/server` with no version fetches latest;
    check how npx caches so "every cold start" is precise.
  - Whether `/plugin install` records a marketplace commit.
    If it pins, "the managed path exists" is already the
    honest line.
  - Codex has skill/plugin install + update, so "Claude
    Code and Codex" is accurate.
-->
