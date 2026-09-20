## Skills

<div style="display: flex; align-items: center; gap: 1.5em;">
<div class="logo"><img class="mark" src="slides/logos/sparkle.svg" /><img class="cel" src="slides/cel-on.svg" /></div>
<div class="code">
<p class="path">~/.claude/skills/deploy-helper/SKILL.md &nbsp;·&nbsp; copied from a repo</p>
<pre><code class="language-markdown">---
name: deploy-helper
description: Use when deploying to staging
---
Run `scripts/deploy.py --env staging`.
Run `npx -y @acme/deploy-cli status`.
Fetch https://acme.dev/deploy-checklist.md and follow it.</code></pre>
</div>
</div>

Note: Pattern four: skills. I do this one now, actively. A skill is a markdown file your coding agent reads and follows. You get one by copying it from someone's repo into a folder the agent scans. It's new, and everyone's sharing.

---

## Skills

<p class="eyebrow">Jank</p>

<ul class="gap">
<li>Marketplaces are git repos</li>
<li>Unpinned by default</li>
<li>Review = reading markdown</li>
</ul>

Note: Claude Code: skills are a folder, marketplaces are git repos, and a plugin is pinned only if its author set a SHA. Codex: skill-installer downloads from a repo and records nothing. The default most people use is unpinned. Review is reading markdown.

---

## Skills

<p class="eyebrow">Risk</p>

<ul class="gap">
<li>An agent, with your credentials</li>
<li>Can fetch more instructions at runtime</li>
<li>Nothing for a scanner to match</li>
</ul>

<p style="font-size: 1.15em; margin-top: 0.8em;"><strong>Skills are software</strong></p>

Note: It runs as you, except now it's an agent with your credentials. It can fetch more instructions at runtime. Your scanners match versions and hashes; a skill has none. It's the shell script again. Skills are software.

<!--
============================================================
BACKMATTER / RAW NOTES
============================================================

The assertion "Skills are software" is a bold line under
the three risk bullets. The bookend ("the shell script again")
stays in the mouth right before it.
Land it and stop; the next slide is the quiet one.

"Nothing in your stack sees this layer" was cut for length;
the EDR line is back in the narration. Say the rest if a slide
runs short.

GRAPHICS: done. Marks in slides/logos/, light is cel-on.svg /
cel-off.svg positioned over the mark by .logo CSS.

VERIFIED (2026-09-17):
  Claude Code (code.claude.com/docs/en/plugin-marketplaces,
  plugins-reference):
  - A skill is a folder under ~/.claude/skills or
    .claude/skills, loaded in place. No version.
  - A marketplace is a git repo (.claude-plugin/
    marketplace.json). Authors MAY pin a plugin with ref,
    a 40-char sha, or a version; unpinned git sources track
    the default branch. The community catalog pins every
    approved plugin to a commit SHA.
  - plugin.json version gates updates: users get a new copy
    only when the author bumps it.
  Codex (learn.chatgpt.com/docs/build-skills):
  - Skills live in .agents/skills or ~/.agents/skills.
    $skill-installer downloads from repos. Docs mention no
    lockfile or commit tracking.
  Vercel npx skills (github.com/vercel-labs/skills):
  - No lockfile. Pin only by putting a ref in the URL.

  So: "nothing is pinned" is false; "unpinned by default"
  is what the docs support.

  Agent Skills spec (agentskills.io/specification), 2026-09-20:
  - scripts/ "contains executable code that agents can run";
    Python, Bash, JavaScript. The spec's own example body is
    "Run the extraction script: scripts/extract.py".
  - No lockfile, integrity hash, or version mechanism in the
    spec. Only an optional free-form metadata map (the
    example shows version: "1.0" as a string in it).
  The SKILL.md on the method slide passes the spec's own validator
  (`uvx --from skills-ref agentskills validate`, 2026-09-20): name
  matches the directory in the caption, required fields present.
  So "Skills are software" and "Unpinned by default" are both
  the spec, not an opinion.

HALLWAY ONLY (scareware register, not for the slide):
  - arXiv 2601.10338 (Jan 2026): 26.1% of audited community
    skills contained a vulnerability; 13.3% data exfil.
  - Orca Security "Skill Issues" (May 2026): submit, pass the
    scan, mutate after the scan; marketplace keeps the clean
    audit.
  Both via Rok Garbas's JCON 2026 deck (~/Downloads/slides.pdf).

STILL TO VERIFY:
  - npx -y @scope/server with no version fetches latest.
-->
