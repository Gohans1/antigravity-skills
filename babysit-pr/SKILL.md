---
name: babysit-pr
description: Use when the user asks to monitor, watch, or babysit a PR.
metadata:
  harness: [claude, codex]
  platform: [darwin, linux]
  scope: fleet
---

# Babysit PR

All the repos we work in have various AI review bots. They're helpful, even if they are not always right.

If your harness offers tools to monitor a PR, use them so you can respond when comments arrive. Otherwise, poll the PR for new comments and checks.

Only act on checks and comments newer than the latest push. Verify every bot finding against the source before changing code. Fix real findings and CI failures, distinguish repository failures from infrastructure flakes, and reply with a written reason when dismissing false positives.

Keep an eye on changes to `main` and rebase when needed. If an overlapping PR makes this one obsolete, stop monitoring, report it to the user, and ask before closing the PR unless closure was explicitly authorized.

If a review bot leaves feedback you believe is not worth addressing, reply and resolve the comment. Format comments left on Theo's behalf as:

> ```md
> [MODEL-SLUG] RESPONDING ON BEHALF OF GOHANS
>
> [actual reply]
> ```

Do not let review feedback expand the PR beyond the user's original goal. Address real shortcomings, but avoid scope creep.
