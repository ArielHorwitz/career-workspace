---
name: firm-job-hunt
description: Find the roles at a firm worth pursuing, and prepare that firm's dossier. Use when the user names a firm or a careers page they want to look at.
disable-model-invocation: true
argument-hint: <firm name or careers-page URL>
---

# Firm job hunt

Finds a firm's open roles, shortlists the ones worth pursuing, and prepares the
firm's dossier following "Applying to a firm" in `README.md`. The user then
decides from the finished dossier which roles, if any, to apply to.

## Governing principle

Every firm's careers site is different. Treat each step that depends on the
site as best-effort: capture whatever is available, don't require any
particular field or format, and use extra information when it happens to be
there. Every such step has a manual fallback. Never spend long trying to crack
a site. Drop to the fallback and keep moving toward the valuable part, the
shortlist and the dossier.

## Process

1. **Read the standing context.** `playbook.md` for how to choose and rank
   roles, `biography.md` for who the user is and what they want, and
   `applications/log.md` plus any existing dossier for the firm, to see what's
   already been pursued.

2. **Retrieve the postings,** cheapest route first: a documented API or data
   feed, then the page itself, then asking the user to paste links or text.
   Many careers pages load their listings from a JSON endpoint behind the page,
   which is easier to read than the page. If a script is worth writing, keep it
   in the firm's dossier so the search can be rerun later.

3. **Capture what each posting exposes:** title, posting id, location,
   seniority, date, description, and a link. Check that each link opens that
   specific posting, since some sites silently fall back to a default page
   when a link is malformed.

4. **Shortlist by fit,** following the playbook. Say which roles genuinely
   fit, which don't and why, and any gate that cuts across them (location,
   eligibility, years of experience). At a large firm, most postings will be
   poor fits. Say so plainly.

5. **Prepare the dossier** for the whole shortlist, without first asking the
   user to pick targets. A finished dossier is easier to decide from than a
   bare list, and preparing one commits the user to nothing: no snapshot and
   no log row until something is actually sent. Follow "Applying to a firm" in
   `README.md` up to, but not including, sending.

6. **Report** the shortlist, the dossier, any headwinds the user should weigh,
   and any suggested change to the resume. Don't edit the resume yourself.
