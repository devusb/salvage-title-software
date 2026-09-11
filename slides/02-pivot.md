<!-- .slide: data-timing="12" -->
## How You Ship to Customers

<ul style="font-size: 0.65em;">
<li>Chainguard base images</li>
<li>Grype in CI</li>
<li>Wiz on the cluster</li>
<li>Signed. SBOM'd. Scanned. Versioned.</li>
</ul>

Note: Now. You all ship software. You ship it well. Hardened base images. A scanner in the pipeline that blocks the deploy. Something watching the cluster. Signatures, SBOMs, versions, provenance. That's how you ship to your customers, and it's real, and you built it.

---

<!-- .slide: data-timing="8" -->
## How You Ship to Yourself

<div class="placeholder" style="width: 640px; height: 200px;">
[GRAPHIC: four logos in a row, each with the check engine light on]<br/>
terminal · Python · Docker · sparkle/plug<br/>
Reprised in 08-close.md, lights on then lights off.
</div>

Note: How do you ship to yourself? Your dev environment. The scripts you run every day. The tools your team uses to do the job. Four patterns. For each one: how it's done, why, because there's always a real reason, and then the gaps. Two kinds of gaps. What's broken, and what's exposed.

<!--
============================================================
BACKMATTER / RAW NOTES
============================================================

TIMING: 0:12 + 0:08.

The tool names are deliberate. Chainguard / Grype / Wiz get
called back on 05-container.md and 06-skills.md. Swap for
whatever the room actually uses if the venue is known.

GRAPHICS NEEDED:
  - four-logo row with lights. Master composite; each
    pattern slide uses one logo+light from it.
-->
