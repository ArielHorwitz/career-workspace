# Agent instructions

This is a career workspace: plain files that the user and AI agents maintain
together. It holds the user's professional history, the resume derived from it,
a record of every job application, and a running journal of their working life.
[`README.md`](README.md) explains what goes where and how the workflows run.
This file holds the principles behind them.

If [`bootstrap.md`](bootstrap.md) exists, the workspace hasn't been set up yet.
Read it before anything else.

Every rule here comes with its reason, so you can tell when a reason doesn't
apply and adapt. When you deviate from a rule, tell the user and say why.

## One source of truth for facts

Every fact about the user's career (roles, dates, what they built, what they
know and how well, what they want) lives in [`biography.md`](biography.md).
Everything else is derived from it and never the other way around.

*Why:* facts copied into several documents drift apart, and in a job search a
drifted fact is a contradiction an interviewer can catch. With one source, a
correction is made once and then reconciled outward.

When a fact changes, update the biography first, then fix every downstream
passage that relied on it in the same change.

## Record claim boundaries, not just claims

The biography records how deep each skill goes and what the user can defend
under questioning. "Used Kubernetes" and "ran production clusters" are different
claims. Note the difference, and note anything uncertain, confidential, or
shared credit.

*Why:* interviewers probe whatever is on the page. An overclaim found out in an
interview costs far more than the omission would have. Writing the boundary
next to the fact lets every downstream document stay honest without
re-interviewing the user.

## Separate facts, strategy, and artifacts

- **Facts** live in `biography.md`.
- **Strategy** (what roles to target, how to position, what has worked with
  recruiters, comp expectations, location rules) lives in
  [`playbook.md`](playbook.md).
- **Artifacts** (the resume, cover notes, interview material) are derived from
  both.

*Why:* they change for different reasons and at different rates. A lesson like
"recruiters screen hard on years of experience" is strategy, and it shouldn't
be buried in one firm's notes or mixed into the user's history.

## The user owns the canon

The resume and anything else the user signs their name to are theirs. Propose
changes to them and explain why, but don't make them unprompted.

*Why:* the user has to stand behind every line in an interview, and an
agent-polished sentence they don't recognize is a liability.

## Freeze what was sent

The moment anything is submitted, forwarded, or received (a resume, a cover
note, a recruiter's email, an offer), a copy goes into that firm's `snapshots/`
directory exactly as it was, and is never edited again.

*Why:* weeks later, when a recruiter calls, the user needs to know exactly what
that recruiter read, and the living resume will have moved on.

## Interview answers are the user's

Help the user prepare for interviews, but don't script what they should or
shouldn't say.

*Why:* what they say is decided in the moment, by them. Prepared lines they
didn't arrive at themselves sound recited and fall apart under a follow-up
question.

## Promote lessons, keep episodes local

When something learned from one application looks like it will hold generally,
promote the rule to the playbook. Leave the story of how it was learned where
it happened. Likewise, durable facts that surface in the journal or a dossier
get promoted into the biography.

*Why:* the playbook and biography are read constantly, so they have to stay
general and current. Doing something twice doesn't make it a rule.

## Plain files, written with judgment

Markdown, plus whatever format the user keeps their resume in. No generators,
schemas, or template pipelines.

*Why:* a resume is distilled through judgment, not assembled from fields. Plain
files also work with any agent, and in a diff.

## Docs form a tree

Each README helps find the docs beneath it. Point down, never up or sideways.

*Why:* a document with no back-references is never left with a stale one.

## Explain why

Anything you write into this workspace that tells a future agent what to do
should say why.

*Why:* a future session that knows the reason can handle the case the rule
didn't anticipate. One that only knows the rule will apply it where it doesn't
fit.

## Keep the workspace private

This workspace holds salary expectations, honest self-assessments, and possibly
an employer's internal details. Never create a remote, push, or publish
anything unless the user explicitly asks. If the user does want a remote, it
should be private.

*Why:* a single public push can't be fully taken back, since it may be copied
or indexed before it's deleted.

## Propose process changes, don't make them

At the end of any substantial piece of work, consider whether the process or
structure could be better: something missing, something redundant, a step that
keeps getting skipped, a doc that keeps confusing sessions. Suggest it to the
user with your reasoning, and make the change only once they agree.

*Why:* this workspace should evolve to fit the user, and the sessions that use
it see where it fits badly. But a workspace that every session rearranges
becomes one no session can trust. The user decides.

## Skills

Reusable workflows live in [`.claude/skills/`](.claude/skills/), one directory
each with a `SKILL.md`. If your agent doesn't load them automatically, read the
matching `SKILL.md` when a task fits its description.

- [`biography-interview`](.claude/skills/biography-interview/SKILL.md):
  interview the user to fill in and deepen the biography.
- [`firm-job-hunt`](.claude/skills/firm-job-hunt/SKILL.md): find the roles at a
  firm worth pursuing, and prepare that firm's dossier.
- [`review-workspace`](.claude/skills/review-workspace/SKILL.md): check the
  workspace for contradictions, drift, and misplaced material.
