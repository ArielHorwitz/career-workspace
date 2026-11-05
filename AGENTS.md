# Agent instructions

This is a career workspace: it holds the user's professional history, resume,
a record of every job application, and a running journal of their working life.
It is designed for the user and AI agents to maintain together.

If [`bootstrap.md`](bootstrap.md) exists, the workspace hasn't been set up yet.
Read it before anything else. Otherwise, read [`README.md`](README.md) before
doing any work here. It explains what goes where and how the workflows run,
and this file only holds the principles behind them.

## Reasons over rules

Rules in this workspace come with their reasons, so you can tell when a reason
doesn't apply and adapt. When you deviate from a rule, tell the user and say
why. Likewise, when you write something that tells a future agent what to do,
say why, so it can handle the case the rule didn't anticipate.

## One source of truth for facts

Every fact about the user's career lives in one place, and everything else is
derived from it, employing the "single source of truth" principle. When a fact
changes, correct the source first, then reconcile what relied on it.

Keep facts apart from strategy (how the user searches and positions
themselves) and from artifacts (the resume, cover notes), since they change
for different reasons and at different rates.

## Honesty about what the user can claim

Record how deep each claim goes, not just the claim. "Used Kubernetes" and "ran
production clusters" are different claims, and interviewers probe whatever is
on the page. Note what's uncertain, confidential, an estimate, or shared
credit. Never fill a gap with an invention.

## The user owns what carries their name

The resume and anything else the user signs is theirs. Propose changes and
explain why, but don't make them unprompted, since the user has to stand
behind every line. Likewise, help them prepare for interviews, but don't
expect them to memorize a script of what to say.

## What was sent stays as sent

Once something is submitted, forwarded, or received, keep a copy exactly as it
was and never edit it. Weeks later, the user needs to know exactly what a
recruiter read, and the living documents will have moved on.

## Promote lessons, keep episodes local

When something learned in one place looks like it will hold generally, promote
the general rule to where it's read broadly, and leave the story where it
happened. Doing something twice doesn't make it a rule.

## Plain files, written with judgment

Markdown, plus whatever format the user keeps their resume in. No generators,
schemas, or template pipelines: a resume is distilled through judgment, not
assembled from fields.

## Docs form a tree

Each README helps find the docs beneath it. Point down, never up or sideways,
so no document is left holding a stale back-reference.

## Keep the workspace private

The workspace holds salary expectations, honest self-assessments, and possibly
an employer's internal details. Never create a remote, push, or publish
anything unless the user explicitly asks, and any remote should be private. A
public push can't be fully taken back.

## Propose process changes, don't make them

At the end of any substantial piece of work, consider whether the process or
structure could be better: something missing, something redundant, a step that
keeps getting skipped, a doc that keeps confusing sessions. Suggest it to the
user with your reasoning, and make the change only once they agree. The
workspace should evolve to fit the user, but one that every session rearranges
becomes one no session can trust.

## Skills

Reusable workflows live in [`.agents/skills/`](.agents/skills/), one directory
each with a `SKILL.md`. If your agent doesn't load them automatically, read the
matching `SKILL.md` when a task fits its description.
