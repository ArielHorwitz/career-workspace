---
name: review-workspace
description: Review the career workspace for contradictions, drift, misplaced material, and broken links. Use after substantial changes to the biography or the workspace's docs, or when the user asks for a review. Not for routine additions or ordinary application work.
---

# Review the workspace

Facts get corrected, strategy evolves, and documents drift apart over time.
This is a bounded pass to catch that, without turning into another session
that rearranges everything.

## Get an independent look

If your agent can launch subagents, give the review to two or more fresh ones,
each with the full task below and none of this session's context, and have
them report back without editing. Overlapping reviewers are deliberate: a
finding several of them reach independently is more trustworthy than one
reviewer's opinion. If you can't launch subagents, do the review yourself,
reading the files fresh rather than relying on what you remember of them.

## What to check

- **Contradictions:** a fact stated one way in the biography and another way
  downstream (playbook, interview material, open dossiers, the resume).
- **Unreconciled changes:** since the last review or the given baseline,
  biography changes that weren't carried to the passages relying on them.
- **Misplaced material:** facts living outside the biography, strategy buried
  in a dossier, episodes in the playbook. Use the "What goes where" table in
  `README.md` as the standard.
- **Overclaims:** downstream wording that claims more than the boundary
  recorded in the biography.
- **Things that must not change:** snapshots edited, or the resume changed by
  an agent without the user asking.
- **Links:** local links and paths that no longer resolve.

## Act with a high bar

Fix objective, low-risk problems directly: a broken link, a stale path, a
direct contradiction where the biography is clearly right. Don't touch the
resume or snapshots, and surface anything about them to the user instead.

Bring structural problems (a document doing two jobs, a recurring confusion)
to the user with a proposal, rather than reorganizing on your own.

Decline stylistic preferences, hypothetical future drift, and suggestions to
add documentation that only restates existing documentation.

## Report

What was checked, what was fixed, what needs the user's decision, and what you
consciously declined and why. Do one round of review and fixes, then stop.
