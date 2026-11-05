# Career workspace

A directory of plain files that an engineer and their AI agents maintain
together. It holds the engineer's professional history, the resume derived from
it, a record of every job application, and a running journal of their working
life. It earns its keep during a job search, and between searches too, when the
material for the next one is being lived.

> **This is a template.** To use it, clone it, open your coding agent in the
> clone, and ask it to read `bootstrap.md`. Don't fork it on GitHub, since a
> fork of a public repository is public and this workspace will hold private
> material.

Agents: the principles behind everything here are in [`AGENTS.md`](AGENTS.md).
This file covers what goes where and how the workflows run.

## What goes where

| Kind of material | Where it lives |
| --- | --- |
| Facts about the user's career, how far each claim goes, and what they want | [`biography.md`](biography.md) |
| Job-search strategy and lessons that carry across applications | [`playbook.md`](playbook.md) |
| The resume | `resume.*`, in whatever format the user prefers |
| Everything about one firm: postings, fit, cover notes, progress | a dossier under [`applications/`](applications/) |
| What was actually sent or received | that dossier's `snapshots/` |
| Where every application stands, at a glance | [`applications/log.md`](applications/log.md) |
| Interview preparation that outlives one interview | [`interview/`](interview/) |
| Raw notes on the user's working life, as it happens | [`journal/`](journal/) |
| Reusable agent workflows | [`.agents/skills/`](.agents/skills/) |

When something doesn't obviously fit, ask what kind of thing it is. A fact goes
to the biography even if it came up while working on one firm. A lesson about
recruiters goes to the playbook even if it came from one application. New
directories (signed reference letters, salary research, and so on) are fine
when the material calls for them. Add them to this table when they appear.

## Updating facts

The biography is the single source of truth for facts. They change there
first, and then the passages elsewhere that relied on the old fact (playbook,
interview material, open dossiers) are reconciled. Snapshots are the exception,
since they record what was sent and stay as they were. If the resume is
affected, tell the user rather than editing it.

## The resume

The resume is canon and the user's to change. Agents review it and propose
improvements, but don't edit it unprompted.

A useful default is one broad resume submitted everywhere, with the per-firm
effort going into the cover note instead. Maintaining a tailored resume per
application costs a lot and mostly produces drift. When a single submission
genuinely needs a different line, that variant is frozen in the firm's
`snapshots/` like any other submission.

## Applying to a firm

Read the playbook and the log first, for the standing strategy and to see
what's already been pursued. Then:

1. Create or reuse `applications/<firm>/`, and save each role's posting under
   its `postings/`. Postings get taken down.
2. In the dossier's README, rank the roles by fit and give each a status line.
   Record positioning decisions and known gaps. Be blunt about poor fits.
3. Hold the resume up against this firm and these roles. Suggest anything
   worth changing to the user, in general or for this one submission.
4. Write the tailored cover note or outreach in the dossier.
5. When the user sends it, freeze what went out in `snapshots/` and add the
   role's row to the log.

The `firm-job-hunt` skill wraps this with finding and shortlisting the roles.
[`applications/README.md`](applications/README.md) has the details of a
dossier and its lifecycle.

## Interview preparation

[`interview/`](interview/) holds preparation that carries across interviews.
Material specific to one firm's interview stays in that firm's dossier.

## The journal

[`journal/`](journal/) is a loose, running record of the user's working life,
kept while it happens rather than reconstructed from memory at the next search.
Agents promote durable facts from it into the biography and lessons into the
playbook.

## Skills

- [`biography-interview`](.agents/skills/biography-interview/SKILL.md):
  interview the user to fill in and deepen the biography.
- [`firm-job-hunt`](.agents/skills/firm-job-hunt/SKILL.md): find the roles at a
  firm worth pursuing, and prepare that firm's dossier.
- [`review-workspace`](.agents/skills/review-workspace/SKILL.md): check the
  workspace for contradictions, drift, and misplaced material.
