## Skills and MCP

<div style="display: flex; align-items: flex-start; gap: 1.2em;">
<div class="placeholder" style="width: 170px; height: 170px; flex: none;">
[GRAPHIC: sparkle or plug icon + check engine light]
</div>
<div style="flex: 1;">
<div class="mwg">
<p class="fragment"><strong>Method</strong> Copy a <code>SKILL.md</code> into <code>~/.claude/skills/</code>. Clone a repo of them. <code>npx -y @scope/server</code> in a JSON file. Claude Code and Codex have plugin systems now: marketplaces, install, update. More than <code>~/bin</code> ever had.</p>
<p class="fragment"><strong>Why</strong> Brand new. Enormous, immediate value. Everyone's sharing. This is the Slack script in 2015, and that was good energy. It's how tooling ecosystems get built.</p>
</div>
<div class="gaps">
<div class="fragment">
<h4>Jank</h4>
<ul>
<li>The managed path exists. Most of what's on your disk didn't come through it</li>
<li>Clone at HEAD. Copied file. <code>npx -y</code> at latest</li>
<li>Review is reading markdown for the one line that says fetch-and-run</li>
</ul>
</div>
<div class="fragment">
<h4>Risk</h4>
<ul>
<li>Runs as you. And "you" is now an agent with your credentials that does what the file says</li>
<li>A malicious skill doesn't need a payload. It needs a sentence</li>
<li>Nothing in your stack sees this layer. No Chainguard for skills. No Grype for <code>~/.claude</code>. Wiz doesn't know the directory exists. SentinelOne is looking for a binary</li>
</ul>
</div>
</div>
</div>
</div>

<p class="fragment" style="font-size: 0.75em; margin-top: 0.5em;">It's the <code>~/bin</code> script again.</p>

Note: Pattern four. Skills and MCP servers. You copy a SKILL.md into a directory. You clone somebody's repo of them. You put npx dash y some-package in a JSON file. And to be fair, Claude Code and Codex both have plugin systems now, with marketplaces and install and update commands, which is more than tilde-bin ever had. Why? Because it's brand new and the value is enormous and everyone is sharing. This is exactly the Slack script in 2015, and that was good energy. This is how tooling ecosystems get built. The jank: the managed path exists, and most of what's on your disk didn't come through it. Review means reading a markdown file looking for the one line that says fetch and run. The risk: it runs as you, except now "you" is an agent holding your credentials that does what the file says. A malicious skill doesn't need a payload. It needs a sentence. And nothing in your security stack sees this layer. There's no Chainguard for skills. Wiz doesn't know the directory exists. SentinelOne is looking for a binary, and the threat is a paragraph. It's the tilde-bin script again.

<!--
============================================================
BACKMATTER / RAW NOTES
============================================================

TIMING: ~0:45. This one gets the extra five seconds.

NARRATE: the Why generously (it earns the Risk), "doesn't
need a payload, it needs a sentence," then the bookend.
Land the bookend and stop. Next slide is the quiet one.

GRAPHICS NEEDED:
  - sparkle (agent) or plug (MCP) glyph with the check
    engine light. Keep it generic, not a vendor logo.

VERIFY:
  - `npx -y @scope/server` with no version fetches latest;
    check how npx caches so "every cold start" is precise.
  - Whether `/plugin install` records a marketplace commit.
    If it pins, the honest line is "the default path
    doesn't pin," which is what the Jank column already says.
  - Codex plugin/skill management: confirm it has install +
    update so "Claude Code and Codex" is accurate.
-->
