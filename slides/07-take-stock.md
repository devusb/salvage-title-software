<div style="display: flex; gap: 4em; justify-content: center; align-items: flex-start; margin-top: 0.6em;">
<div style="text-align: center;">
<img src="slides/cel-on.svg" style="height: 200px; display: block; margin: 0 auto; border: none; box-shadow: none; background: none;" />
<p style="font-size: 0.95em; margin: 0.5em 0 0 0;"><code>xz</code></p>
</div>
<div style="text-align: center;">
<img src="slides/cel-on.svg" style="height: 200px; display: block; margin: 0 auto; border: none; box-shadow: none; background: none;" />
<p style="font-size: 0.95em; margin: 0.5em 0 0 0;">Nx Console VS Code extension</p>
</div>
</div>

### Did anything change? <!-- .element: style="font-size: 0.9em; margin-top: 0.8em" -->

Note: xz: two years earning trust to backdoor a library that ends up inside sshd. In May, the Nx Console VS Code extension, poisoned, on one GitHub laptop: thirty-eight hundred internal repos. Neither was broken. They worked perfectly, for someone else. Do you have sandbox hygiene? I don't.

<!--
============================================================
BACKMATTER / RAW NOTES
============================================================

Morgan is keeping this slide (2026-09-17).

The quiet slide. Two logos, one question.

VERIFY:
  - xz: CVE-2024-3094, March 2024, liblzma, sshd via the
    systemd notification patch. One sentence.
  - IDE extension compromise, VERIFIED 2026-09-17: Nx Console
    (nrwl.angular-console, ~2.2M installs, verified publisher)
    was backdoored on the VS Marketplace for 18 minutes on
    2026-05-18. A GitHub employee installed it; GitHub
    confirmed on 2026-05-20 that ~3,800 internal repos were
    taken. The stealer harvested npm, GitHub, AWS, 1Password
    and Claude Code credentials. TeamPCP claimed it.
    bleepingcomputer.com/news/security/github-confirms-breach-
    of-3-800-repos-via-malicious-vscode-extension/
    thehackernews.com/2026/05/github-internal-repositories-
    breached.html

GRAPHICS: done. Two lights over plain text, same layout as
the Production and Ours slides. No wordmark files.
-->
