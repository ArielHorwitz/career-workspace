# Career workspace bootstrap

This document sets up a career workspace: a directory of plain files that
an AI coding agent and an engineer maintain together. It holds the engineer's
professional history, the resume derived from it, a record of every job
application, and a running journal of their work. It is useful during a job
search, and just as useful between searches, when the material for the next one
is being lived.

It came out of one engineer's job search and was rewritten to be generic. The
structure and principles carried over. The specifics did not, and should not be
guessed at.

**To use it:** put this file in an empty directory, open your agent there, and
ask it to read `bootstrap.md` and set up your career workspace.

The rest of this document is addressed to that agent.

---

## How to read this document

This is a starting point, not a specification. The user may work in a very
different corner of software engineering, a different market, or a different
stage of their career than the person this came from. Every rule below comes
with its reason, so you can tell when the reason doesn't apply to this user and
adapt. Where you deviate, tell the user and say why.

Don't build everything at once. Set up the core, run the bootstrap interview,
and add the rest when the user actually needs it. An empty file nobody uses is
clutter that future sessions will waste time reading.

Once the workspace exists, its own docs are the authority, not this file.
Distil what applies into the workspace's `AGENTS.md` and `README.md` so a
future session never needs to come back here.

## Principles

### One source of truth for facts

Every fact about the user's career (roles, dates, what they built, what they
know and how well, what they want) lives in one file, `biography.md`.
Everything else, the resume, cover notes, interview prep, is derived from it
and never the other way around.

*Why:* facts copied into several documents drift apart, and in a job search a
drifted fact is a contradiction an interviewer can catch. With one source, a
correction is made once and then reconciled outward.

When a fact changes, update the biography first, then fix every downstream
passage that relied on it in the same change.

### Record claim boundaries, not just claims

The biography records how deep each skill goes and what the user can defend
under questioning. "Used Kubernetes" and "ran production clusters" are
different claims. Note the difference, and note anything that is uncertain,
confidential, or shared credit.

*Why:* interviewers probe whatever is on the page. An overclaim found out in an
interview costs far more than the omission would have. Writing the boundary
next to the fact lets every downstream document stay honest without
re-interviewing the user.

### Separate facts, strategy, and artifacts

- **Facts** live in `biography.md`.
- **Strategy** (what roles to target, how to position, what has worked with
  recruiters, comp expectations, location rules) lives in `playbook.md`.
- **Artifacts** (the resume, cover notes, interview scripts) are derived from
  both.

*Why:* they change for different reasons and at different rates. A lesson like
"recruiters screen hard on years of experience" is strategy and shouldn't be
buried in a firm's notes or mixed into the user's history.

### The user owns the canon

The resume and anything else the user signs their name to are theirs. Agents
propose changes to them and explain why, but don't make them unprompted.

*Why:* the user has to stand behind every line in an interview, and an
agent-polished sentence they don't recognize is a liability.

### Freeze what was sent

The moment anything is submitted, forwarded, or received (a resume, a cover
note, a recruiter's email, an offer), a copy goes into that firm's
`snapshots/` directory exactly as it was, and is never edited again.

*Why:* weeks later, when a recruiter calls, the user needs to know exactly what
that recruiter read, and the living resume will have moved on.

### The firm is the unit

One dossier per firm, covering every role pursued there.

*Why:* a firm evaluates a candidate across its open roles, and a recruiter at
one firm will remember the user from the last role they applied to there.

### Explain why

Anything an agent writes into this workspace that tells a future agent what
to do should say why. That applies to this document and to every doc it
creates.

*Why:* a future session that knows the reason can handle the case the rule
didn't anticipate. One that only knows the rule will apply it where it doesn't
fit.

### Promote lessons, keep episodes local

When something learned from one application looks like it will hold
generally, promote the rule to the playbook. Leave the story of how it was
learned in the dossier.

*Why:* the playbook is read before every application, so it has to stay short
and general. Doing something twice doesn't make it a rule.

### Plain files, written with judgment

Markdown and maybe one HTML resume. No generators, schemas, or template
pipelines.

*Why:* a resume is distilled through judgment, not assembled from fields.
Plain files also work with any agent, and in a diff.

### Docs form a tree

Each README helps find the docs beneath it. Point down, never up or sideways.

*Why:* a document with no back-references is never left with a stale one.

## Suggested layout

```
AGENTS.md            agent instructions: principles, conventions, pointers
CLAUDE.md            contains only `@AGENTS.md`, for Claude Code
README.md            what goes where, and the workflows
biography.md         the facts
playbook.md          the strategy
resume.*             the resume, in whatever format the user prefers
journal/             the running career journal
applications/
  log.md             one row per role applied to: firm, role, status, link
  <firm>/
    README.md        roles ranked by fit, positioning, status, progress
    postings/        each role's posting text
    snapshots/       what was sent or received, frozen
interview/           added when interviews start (see below)
```

Rename and reshape freely. The user may already have conventions they
prefer, and those win.

Other agents read `AGENTS.md` directly. Claude Code reads `CLAUDE.md`, and the
`@AGENTS.md` line imports the shared file. A symlink works too, but the import
also works on Windows.

### Version control

Suggest making the directory a git repository. It's free history, and it lets
the user see exactly what an agent changed. If they want to sync it between
machines, a private remote is the way. This workspace will hold salary
expectations, honest self-assessments, and possibly an employer's internal
metrics, so it should never be public. Don't create a remote or push anything
yourself.

## Bootstrap

### 1. Gather existing material

The user won't remember everything that might help, so offer a list and let
them pick:

- an existing resume or CV, including old versions
- a LinkedIn profile (its "Get a copy of your data" export is far more
  complete than anything scraped from the page)
- GitHub or GitLab profiles, and specific repositories worth reading
- a personal website or portfolio
- talks, articles, blog posts, open-source contributions
- performance reviews, promotion write-ups, peer feedback
- reference or recommendation letters
- old cover letters, and past job postings they applied to
- anything they'd tell a friend about what they've done and what they want
  next

Read everything before asking a single question, so the interview doesn't
spend the user's patience on things already written down.

### 2. Interview the user

Then interview them to fill in the biography. Go broad before deep, and
highest value first. The user's patience is finite and you don't know how
much there is, so order the questions so that stopping at any point leaves
the biography as useful as it could be.

A reasonable order:

1. The skeleton: each role with dates, title, and a sentence on what the job
   was. What they want next, and what they want to avoid.
2. For each role, the one or two things they're proudest of, and any numbers
   attached to them.
3. Skills, and honestly how deep each goes.
4. Stories in detail, the context around each role, and the long tail.

Ask a few questions at a time, not a wall of them. Accept "I don't remember"
and "skip" without pushing, and note the gap.

Impact is what recruiters look for most, and numbers make it believable. Most
engineers don't track it, so press gently on every story for what changed
because of the user's work, and how much. An estimate the user can defend is
fine, if it's recorded as an estimate.

### 3. Leave suggestions for next time

If the interview ends early, write down the questions you would have asked
next, in a clearly non-binding "Suggested questions" section at the end of the
biography. A later session may use them, or ignore them and ask something
better. A fresh session sees things this one missed, so the list shouldn't
box it in.

### 4. Write the playbook and the resume

Draft `playbook.md` from what the user said they want: role types, seniority,
location and remote rules, comp expectations, deal-breakers. It starts thin
and grows with the search.

If the user has a resume, review it against the biography and suggest
improvements. If they don't, draft one for them to rework. Either way it ends
up theirs (see "The user owns the canon").

A useful default is one broad resume submitted everywhere, with the per-firm
effort going into the cover note instead. Maintaining a tailored resume per
application costs a lot and mostly produces drift.

## Applying

For each firm the user is interested in:

1. Create or reuse `applications/<firm>/`. Save each role's posting under
   `postings/`, since postings get taken down.
2. In the dossier's README, rank the roles by fit and give each a status line.
   Record positioning decisions and known gaps. Be blunt about poor fits.
3. Hold the resume up against this role and posting. Suggest anything worth
   changing, in general or for this one submission, to the user.
4. Write the tailored cover note or outreach in the dossier.
5. When the user sends it, freeze what went out in `snapshots/` and add the
   role's row to `applications/log.md`.

Keep each status current in both the dossier and the log. The log answers
"where does everything stand?" at a glance, and the dossier has the detail.

Searching a firm's careers page for fitting roles is worth automating once
the user does it more than a few times. Many careers pages load their listings
from a JSON endpoint that is easier to read than the page. When a site
resists, fall back to the user pasting links and move on.

## Interview preparation

Add an `interview/` directory when interviews start. Each of these earned its
place:

- **A spoken self-introduction**, in a two-minute version for hiring managers
  and a thirty-second one for HR screens. Every interview starts with "tell me
  about yourself."
- **A story bank**: the user's best stories, each with the point it makes and
  the questions it answers.
- **A question bank**: a long, wide list of questions the user might face,
  with no prepared answers. Its purpose is reducing surprises. The user skims
  it, notices where they don't have even a sketch of an answer, and prepares
  those. Generating it from several angles (technical, adversarial,
  behavioral) helps, as does phrasing each question from what the interviewer
  can actually see: the resume, LinkedIn, and public profiles.

What the user says in an interview is theirs, decided in the moment. Help
them prepare, but don't script them.

## The journal

The journal is a running record of the user's working life, kept while it
happens rather than reconstructed from memory at the next search. It is
deliberately loose: dated entries, raw notes, no fixed format.

The most valuable things to capture are impact and stories. What changed
because of the user's work, with numbers whenever there are any. Problems
they solved and how. Praise they got. Tools and technologies they used or
learned, and how deeply. Bad experiences belong here too: mistakes, friction,
and what made a team or role a poor fit. They are lessons, and they help the
user judge future roles.

Durable facts get promoted into the biography and lessons into the playbook,
as they become clear. The journal stays raw.

This part has the least experience behind it. Start minimal and let the user
and future sessions work out what makes it useful. Mind confidentiality:
note which details are internal to an employer so they never reach public
copy.

## Keep improving the process

At the end of any substantial piece of work, consider whether the process
or structure could be better: something missing, something redundant, a step
that keeps getting skipped, a doc that keeps confusing sessions. Suggest it
to the user with your reasoning. Don't make structural or process changes on
your own initiative.

*Why:* this workspace should evolve to fit the user, and sessions that use it
see where it fits badly. But a workspace that every session rearranges
becomes one no session can trust. The user decides.

## Seeds for the playbook

Lessons from the search this came from. They are observations from one
search in one market, not rules. Offer them to the user and keep the ones
that hold.

- **Apply on a partial match.** A long requirements list usually describes
  an ideal candidate, not a cut-off.
- **Years of experience is a harder gate than the rest.** Recruiters flex
  most requirements but screen strictly on stated years, and may not count
  non-professional work toward them.
- **Never fill a gap with an invention.** Gaps shape honest positioning and
  interview prep. Invented titles, degrees, or keywords come out in the
  interview.
- **Every public claim must pass three tests.** It is defensible at the depth
  it implies, it is relevant to the reader, and it attracts work the user
  actually wants.
- **A signed reference letter is a ceiling.** Don't publicly claim more about
  that employer than the reference signed, unless the user decides otherwise.
