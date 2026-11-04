# Bootstrap

This file is addressed to the agent setting up a freshly cloned career
workspace. Read [`AGENTS.md`](AGENTS.md) and [`README.md`](README.md) first.
They explain the workspace, and this file only covers the one-time setup.

Setup can span several sessions. Tick each step's box and commit as it's
done, so the next session knows where things stand. Any step may be adapted
or skipped if it doesn't fit this user. Tell them why.

The workspace came out of one engineer's job search and was made generic. The
user may work in a very different corner of the industry, a different market,
or a different stage of their career. Expect to adapt it, and suggest changes
where it fits them badly (see "Propose process changes" in `AGENTS.md`).

## Steps

- [ ] **Make the workspace private.** Run `git remote remove origin` and
  explain to the user why: the clone still points at the public template, and
  this workspace will soon hold private material. If they want to sync it
  between machines, suggest a private remote they set up themselves.

- [ ] **Make the workspace theirs.** Remove the template notice from
  `README.md`. Ask whether they prefer other names or a different layout, and
  whether they want the docs in another language, and adapt the workspace
  before it fills up, while that's cheap.

- [ ] **Gather existing material.** The user won't remember everything that
  might help, so offer a list and let them pick:
  - an existing resume or CV, including old versions
  - a LinkedIn profile (its "Get a copy of your data" export is far more
    complete than anything scraped from the page)
  - GitHub or GitLab profiles, and repositories worth reading
  - a personal website or portfolio
  - talks, articles, blog posts, open-source contributions
  - performance reviews, promotion write-ups, peer feedback
  - reference or recommendation letters
  - old cover letters, and past job postings they applied to
  - anything they'd tell a friend about what they've done and what they want
    next

  Read all of it, and fold what you learn into `biography.md`, before asking
  the user a single question.

- [ ] **Interview the user.** Use the `biography-interview` skill. This step is
  done once the biography has the skeleton (every role, and what the user wants
  next) and the highlights of each role. Deepening it from there is ongoing
  work, not setup.

- [ ] **Draft the playbook** from what the user wants: role types, seniority,
  location rules, comp expectations, deal-breakers. It starts thin and grows
  with the search. Go through its "Starting observations" with the user, and
  keep only the ones that hold for them.

- [ ] **Set up the resume.** Ask what format they want to keep it in. If they
  have a resume, bring it in as `resume.<ext>`, review it against the
  biography, and suggest improvements. If they don't, draft one for them to
  rework. Either way, it ends up theirs.

- [ ] **Finish.** Tell the user setup is done and what comes next (applying to
  firms, starting the journal, interview prep when it's time). With their
  agreement, delete this file and commit, so future sessions stop treating the
  workspace as unfinished.
