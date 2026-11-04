# Applications

One directory per firm, named by a short slug of the firm's name (`acme/`).
Each is a dossier: everything about the user's pursuit of that firm, across
every role, from preparation to outcome. [`log.md`](log.md) is the at-a-glance
table of every application's status.

The firm is the unit, not the role, because a firm evaluates a candidate across
its open roles, and a recruiter will remember the user from the last role they
applied to there.

## A dossier

- `README.md`: the firm, its target roles ranked by fit (each with a status
  line), positioning decisions, known gaps, and progress as it happens
  (correspondence, interviews, outcome).
- `postings/`: each role's posting text, one file per role, named by the
  posting's id or a short role slug. Postings get taken down, so save them
  early.
- The cover note or outreach for the firm, editable until it's sent.
- `snapshots/`: frozen copies of what was sent or received (see below).
- Anything else specific to the firm: research, interview notes, a script used
  to pull its listings.

A dossier holds no resume of its own. The workspace resume is what gets
submitted, and the copy that went out lives in `snapshots/`.

## Snapshots

The freeze attaches to events, not to files. The moment something is
submitted, forwarded, or received, a copy goes into `snapshots/` exactly as it
was, and is never edited again. That covers:

- the resume as submitted to a role or handed to a referrer
- the cover note or outreach as sent, dated
- correspondence and documents received, such as a reply, an offer, or a
  take-home brief, named so the kind, role, and date are clear

Drafts that were never sent leave no snapshot.

*Why:* weeks later, when a recruiter calls, the user needs to know exactly what
that recruiter read, and the living resume and cover note will have moved on.

## Status

Keep each role's status current in both the dossier and its row in the log.
Add a role's row when it's applied to or referred, not while it's only being
considered. Preparing a dossier commits the user to nothing.

Dossiers are records of each search as it was run. When workspace conventions
change later, don't sweep the changes back into old dossiers.
