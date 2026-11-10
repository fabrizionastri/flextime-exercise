# FlexTime — Full-Stack Technical Assignment

A shared availability & activity coordination platform.

---

## The scenario

Imagine you have a hundred friends and, most evenings, you'd like to do
*something* with *someone* — tennis, a coffee, a movie, a board-game night.
The problem is you never know who is free or what they feel like doing, and you
are not going to message a hundred people every single day.

**FlexTime** solves this. You publish a calendar of the time slots when you are
available, and for each slot you propose one or more activities. You share a
single private link with your friends (over WhatsApp, email, anywhere). They
open it, see your availability, and tell you which activities they're interested
in. Everything else happens offline.

Your task is to build this product end-to-end.

---

## What you will build

A web application that lets a user:

- Manage their own **availability calendar**.
- Propose **activities** during their available time slots.
- Share their calendar with other users via a private link.
- Browse calendars that others have shared with them.
- **Express interest** in activities proposed by others.
- Coordinate activities through a simple, intuitive interface.

The full functional brief — domain model, business rules, statuses, views, and
API — lives in **[specifications.md](specifications.md)**. Read it carefully; it
is the source of truth for *what* to build.

---

## What we are evaluating

This is a deliberately open-ended, scenario-based assignment that mirrors
real-world work. We are interested not only in *what* you build, but in *how*
you decide what to build. We will look at:

- **Product thinking** — turning business needs into a working product.
- **Handling ambiguity** — making and documenting reasonable assumptions.
- **Full-stack architecture** — the Django API, the React frontend, and the
  seams between them.
- **Data modeling** — translating the domain into a clean schema.
- **API design** — clear, consistent, RESTful endpoints.
- **Authentication & authorization** — a passwordless flow that works across
  the API and the frontend, and access control enforced by the API.
- **Frontend UX/UI** — usable, sensible interfaces and workflows.
- **Code quality & maintainability.**
- **Documentation & testing strategy.**

> A smaller but well-designed solution is strongly preferred over a larger but
> poorly structured one.

---

## Working with ambiguity

This specification focuses on the core business requirements. As in any real
project, **some requirements are intentionally left unspecified** — screens,
edge cases, validation rules, and minor workflows.

You are expected to:

- make reasonable assumptions and use your own product and UX judgment,
- design sensible workflows and handle edge cases appropriately,
- and **document the important assumptions** in your project README.

Part of the evaluation is seeing how you transform high-level requirements into
a coherent, working product — and how you decide what *not* to build.

---

## Technical requirements

We are moving FlexUp's products to a **Django REST API** with a separate
**React frontend**, so we ask you to build FlexTime the same way.

| Layer        | Choice                                                      |
| ------------ | ----------------------------------------------------------- |
| **Backend**  | **Django**. Exposes a REST API (JSON).          |
| **Frontend** | **React**. A separate app that uses the API.    |
| **Database** | SQLite.                                       |
| **API**      | **REST**. The only link between the two apps.   |

> **About the architecture:** the backend serves data, not pages. Please don't
> build the user-facing screens with Django templates (DTL) — every screen
> lives in the React app and gets its data from the API. The Django admin is
> fine as an internal tool for yourself. The operations the API must cover are
> listed in [specifications.md](specifications.md#api-requirements).

You may use any other modern, well-justified libraries on top of this (for
example Django REST Framework for the API, or Vite to scaffold the React app).

### Decisions at the seam

A decoupled frontend raises a few questions that a single Django app doesn't.
They are yours to answer — just document your choices in `SOLUTION.md`:

- **Authentication** — how the React app keeps a user signed in against the API
  (session cookie, token, …), and how the sign-in link from the email ends up
  in the React app and gets verified by the API.
- **Local development** — how the frontend reaches the API (a dev-server proxy,
  CORS, …) and, if you use cookies, how you handle CSRF.

### Repository layout

Keep both apps in this one repository, for example:

```
flextime-<your-name>/
├── backend/            # Django project (REST API)
├── frontend/           # React app
├── README.md           # assignment docs — keep them
├── specifications.md
├── SUBMISSION.md
└── SOLUTION.md         # your write-up
```

### Security expectations

Reasonable security practices are expected. In particular:

- Calendar URLs must **not be enumerable**.
- A user may only access a calendar through a valid shared URL or an existing
  Calendar Access relationship.
- The **API enforces every access rule itself**. Hiding something in the React
  UI is not enough — a user calling the API directly must not get data they
  are not allowed to see.

---

## Getting started

Start by **cloning this repository and making it your own**, so the assignment
docs travel with your code. There is no starter application — you scaffold the
Django backend and the React frontend yourself.

1. Clone this repo, rename it as `flextime-<your-name>`, and point it at a new public repo of your own
   (see **[SUBMISSION.md](SUBMISSION.md)** for the exact steps).
2. Scaffold the Django backend and the React frontend inside it (see
   [Repository layout](#repository-layout)) and commit early and often.
3. Build toward the brief in **[specifications.md](specifications.md)**,
   prioritizing the core flow first.
4. Document your decisions in a `SOLUTION.md` (see SUBMISSION.md).

---

## Expected effort and timeline

This assignment is intentionally **larger than most candidates can fully
complete** in the time available. We estimate roughly **10–20 hours of work**,
to be submitted within **one week**. If you need more time, just ask for an
extension.

You are **not** expected to implement every feature. The goal is not to measure
hours invested, but to evaluate technical skill, prioritization, product
thinking, and implementation quality. We encourage you to:

- prioritize the important functionality first,
- make reasonable assumptions and document your trade-offs,
- and clearly explain what you completed, what you left out, and what you would
  build next.

---

## Documentation

- **[specifications.md](specifications.md)** — the full functional brief.
- **[SUBMISSION.md](SUBMISSION.md)** — how to set up your repo and submit.

When you submit, add a `SOLUTION.md` (or a marked section in the README)
explaining your architecture decisions, assumptions, trade-offs, completed and
omitted features, and future improvements.
