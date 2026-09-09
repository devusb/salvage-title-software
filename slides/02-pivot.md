## How You Ship to Customers

<ul style="font-size: 0.65em;">
<li class="fragment">Chainguard base images</li>
<li class="fragment">Grype in CI</li>
<li class="fragment">Wiz on the cluster</li>
<li class="fragment">Signed. SBOM'd. Scanned. Versioned.</li>
</ul>

Note: Now. You all ship software. You ship it well. Hardened base images. A scanner in the pipeline that blocks the deploy. Something watching the cluster. Signatures, SBOMs, versions, provenance. That's how you ship to your customers, and it's real, and you built it.

---

## How You Ship to Yourself

<div class="placeholder" style="width: 640px; height: 200px;">
[GRAPHIC: four logos in a row, each with the check engine light on]<br/>
terminal · Python · Docker · sparkle/plug<br/>
Same row is reprised in 08-close.md with the lights going out.
</div>

Note: How do you ship to yourself? Your dev environment. The scripts you run every day. The tools your team uses to do the job. Four patterns. For each one, how it's done, why it's done that way, because there's always a good reason, and then the gaps. The gaps come in two flavors: the stuff that's broken, and the stuff that's exposed.

<!--
============================================================
BACKMATTER / RAW NOTES
============================================================

TIMING: ~0:20 for both slides.

The tool names are deliberate. Chainguard / Grype / Wiz get
called back on 05-container.md ("your dev image saw none of
those") and 06-skills.md ("nothing in your stack sees this
layer"). Swap for whatever the room actually uses if the
venue is known.

GRAPHICS NEEDED:
  - four-logo row with lights. This is the master composite;
    each pattern slide uses one logo+light from it.

Second slide explains the Method / Why / Jank / Risk layout
in one sentence so the pattern slides don't have to.
-->
