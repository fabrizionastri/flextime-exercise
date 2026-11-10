# FlexTime — Submission Guide

How to set up your repository, work, and submit your solution. For the
assignment itself see **[README.md](README.md)** and
**[specifications.md](specifications.md)**.


## 1. Set up your repository

Start by **cloning this repository and making it your own**. This keeps the
assignment docs (`README.md`, `specifications.md`, and this file) alongside your
code.

1. Clone the challenge repository and enter it:

   ```bash
   git clone <challenge-repo-url> flextime-<your-firstname>
   cd flextime-<your-firstname>
   ```

2. Create a new **public** GitHub repository named `flextime-<your-firstname>`
   and point your clone at it:

   ```bash
   git remote set-url origin https://github.com/<your-username>/flextime-<your-firstname>
   git push -u origin main
   ```

3. Scaffold the Django backend and the React frontend inside the repository
   (see [Repository layout](README.md#repository-layout)) and commit:

   ```bash
   git add .
   git commit -m "Initial Django and React scaffold"
   git push
   ```


## 2. How to work

- **Commit early and often.** Make small, focused commits with clear,
  descriptive messages — they help us understand your thought process.
- **Prioritize the core flow first** (calendar → slot → activity → interest),
  then layer on access control, statuses, and the consolidated view.
- **Make and record assumptions** as you go; don't block on ambiguity.


## 3. The write-up you must provide

Because you keep the assignment's `README.md` and `specifications.md`, document
your own work in a separate **`SOLUTION.md`** (or a clearly marked section at the
top of the README). It is part of the evaluation and should explain:

- **Setup instructions** — how to install dependencies, run migrations, and
  start both the Django API and the React app (assume a reviewer who has never
  seen your project).
- **Architecture decisions** — the shape of your solution and why, including
  how the React app authenticates against the API.
- **API overview** — your endpoints at a glance (a short table, or a link to
  generated OpenAPI docs).
- **Assumptions** — the important calls you made where the brief was silent.
- **Trade-offs** — what you chose and what you gave up.
- **Completed features** — what works.
- **Omitted features** — what you intentionally left out, and why.
- **Future improvements** — what you would build next with more time.


## 4. What to deliver

- A **source code repository** (public, on GitHub), cloned from this one.
- **Setup instructions** that let a reviewer run the backend and the frontend
  locally.
- The **`SOLUTION.md`** write-up described above.


## 5. Submit

When you're done, make sure your repository is **public** and share the link
with us.

If you need more time than the one-week window, just ask — extensions are fine.
A smaller, well-designed and well-documented solution is preferred over a large,
poorly structured one.
