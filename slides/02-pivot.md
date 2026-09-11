<div style="display: flex; gap: 2.5em; justify-content: center; align-items: flex-start; margin-top: 0.4em;">
<div style="text-align: center; flex: 1;">
<div class="placeholder" style="width: 260px; height: 160px;">
[GRAPHIC: check engine light, OFF]
</div>
<p style="font-size: 0.6em; margin: 0.6em 0 0.2em 0;">Production</p>
<p style="font-size: 0.5em; opacity: 0.75; margin: 0;">Cut. Tagged. Promoted. Shipped.</p>
</div>
<div style="text-align: center; flex: 1;">
<div class="placeholder" style="width: 260px; height: 160px;">
[GRAPHIC: check engine light, ON]
</div>
<p style="font-size: 0.6em; margin: 0.6em 0 0.2em 0;">Internal tooling</p>
</div>
</div>

Note: We have elaborate release processes for the artifacts we ship to users. Cut, tagged, promoted, never rebuilt. For internal tooling and dev environments, I have found myself using a lot of anti-patterns. This talk is those anti-patterns, next to how we ship production software.

---

## Four Anti-Patterns I've Shipped

<div class="placeholder" style="width: 640px; height: 200px; margin-top: 0.6em;">
[GRAPHIC: four logos in a row, each with the light on]<br/>
terminal · Python · Docker · sparkle/plug
</div>

Note: Four of them. For each: how it's done, why, because there's always a real reason, and the gaps. What's broken, and what's exposed.

<!--
============================================================
BACKMATTER / RAW NOTES
============================================================

First slide is the divide: production on the left with the
light off, internal tooling on the right with the light on
and nothing under it. The imbalance is the point; the next
slide fills in the right side.

Second slide's title uses first person on purpose. The
whole talk is a confession and the roster is where that has
to be unmistakable. Only exception to the no-first-person
convention in the deck.

PROVISIONAL: "Cut. Tagged. Promoted. Shipped." Morgan does
not like this line yet. Release engineer vocabulary was the
ask; the security-team version (Signed. Attested. Scanned.
Pinned.) was rejected as the wrong register. Revisit once
the graphics exist. In the two-column layout it is a
caption, not a headline, which may be enough.

The four terms are called back on 05-container.md.

GRAPHICS NEEDED:
  - check engine light icon, unlit and lit, side by side.
  - four-logo row with lights. Master composite; each
    pattern slide uses one logo+light from it. Reprised in
    08 lit and dark.
-->
