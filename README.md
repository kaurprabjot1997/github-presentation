# GitHub for Commercial Banking Loan Portfolio Management

This folder contains an interactive, single-page internal-team presentation for a discussion on how GitHub can improve visibility, consistency, and governance across portfolio reporting workflows within our team, plus a companion talk track for a ~25-minute session (20 minutes of talking, ~5 minutes of Q&A).

It is designed for colleagues who are already onboarded to GitHub as well as those who are still learning the workflow and standards.

## Files

- `github_for_loan_portfolio_team.html` — interactive single-page internal overview, built for live presenting:
  - a scroll progress bar and a scrollspy navigation bar that highlights the section currently in view
  - a **time-savings visualization** in "Why GitHub is relevant" — a hover/keyboard-interactive chart showing the short-term learning-curve cost versus the longer-run time saved per reporting cycle, with a table-view fallback
  - a clickable **command lab** covering `clone → pull → branch → status → commit → push → pull request → merge`, where each command drives a small local-machine ⇄ GitHub animation showing exactly what moves (or doesn't move) between your machine and the remote repository
  - an **onboarding checklist** that teammates can check off live; progress is saved locally in their browser

## What is GitHub?

GitHub is a shared platform for storing, reviewing, and tracking changes to code and logic. It helps teams keep a single version of the truth for scripts, ETL work, queries, and reporting logic. It records who changed something, when it changed, and whether it was reviewed before moving to production.

GitHub is useful because it gives teams a structured, traceable way to manage work instead of relying on local copies or ad hoc updates.

## What is JupyterHub?

JupyterHub is a shared notebook environment used for exploring data and testing analytical logic. It is often used when analysts or data engineers need to investigate data, validate assumptions, and prototype calculations before finalizing the logic for broader use.

## When do we use Python and PySpark?

Python is used for scripting, data prep, automation, and ETL logic. PySpark is used when we need to process larger datasets or run distributed transformations efficiently. These tools are typically used when we are turning raw data into cleaned, validated, and reusable portfolio logic.

## What is Airflow?

Airflow is used to schedule and orchestrate jobs in a repeatable, controlled way. It is useful when tasks must run on a schedule, depend on one another, or need to move through staging and production with governance.

## What is Tableau?

Tableau is used for reporting, dashboards, and business-facing data visibility. It turns validated data into curated views for decision support, while GitHub governs the underlying logic that feeds the reporting.

## Session timing at a glance

Total session: **~25 minutes** (20 minutes of talking, ~5 minutes of open Q&A).

| Time | Stage | Page section to be on |
|---|---|---|
| 0:00–1:30 | Opening and context | Hero |
| 1:30–5:00 | What each tool is and why it matters | What each tool does |
| 5:00–10:00 | Why GitHub matters for this team, incl. the time-savings chart | Why GitHub is relevant |
| 10:00–12:30 | Our current workflow | How our team works today |
| 12:30–15:30 | Branching strategy and governance | Branching strategy |
| 15:30–18:30 | GitHub commands in practice | GitHub in action |
| 18:30–20:00 | Onboarding, closing, and Q&A transition | Onboarding to JupyterHub |
| 20:00–25:00 | Open Q&A | — |

## 20-minute speaking script

### 1) Opening and context (0:00–1:30)

“Good morning everyone. Thank you for taking the time to join this discussion.

The purpose of this conversation is not to present GitHub as a technical mandate, but to share the working model our internal team has adopted and to help align colleagues who are already onboarded with those who are still learning the process.

We rely on a combination of JupyterHub, Python, PySpark, Airflow, Tableau, and GitHub to support how we manage reporting logic and data workflows. This is not about forcing everyone onto the same platform overnight — it's about creating a common working standard within our team so that logic is more visible, easier to review, and more consistent across our reports.

If you want to follow along, there's a progress bar at the top of the page tracking where we are in the agenda.”

### 2) What each tool is and why it matters (1:30–5:00)

“Before we talk about the value of GitHub, it helps to agree on the broader environment we're working in — this is the 'What each tool does' section on the page.

GitHub is a shared platform for storing, reviewing, and tracking changes to code and logic. It gives the team a single place to manage scripts, ETL work, and reporting logic, and a record of who changed something, when, and whether it was reviewed before it moved to production.

JupyterHub is a shared notebook environment for exploring data, validating assumptions, and testing analysis — typically where team members start, looking at raw data and experimenting with logic before it's formalized.

Python and PySpark are what we use to process the data itself. Python handles scripting, data preparation, automation, and ETL logic. PySpark steps in when we need to process larger datasets or run distributed transformations efficiently. In practical terms, these tools turn raw portfolio data into cleaner, validated, reusable logic.

Airflow is the scheduling and orchestration layer — it runs jobs in a controlled, repeatable way and coordinates work from one stage to the next, which is what moves us from manual execution to reliable operational execution.

And Tableau is the reporting and business-facing layer. Put simply: GitHub governs the logic, and Tableau is where that logic becomes something the business looks at and acts on. None of these tools live in separate worlds — GitHub sits around them and makes the whole process more consistent and transparent.”

### 3) Why GitHub matters for this team (5:00–10:00)

“So why does that matter for us specifically? This is the 'Why GitHub is relevant' section.

In many analytical environments, logic sits in different places — a SQL query, a notebook, a script, a Tableau workbook, or someone's local working copy. Over time that creates fragmentation. Different people interpret the same business definition slightly differently. A metric changes, a filter gets updated, and not everyone knows why or when.

GitHub gives us a shared place to store and manage that logic, and a record of where it lives, who changed it, why, and when. That matters in portfolio reporting because small changes can have real implications — whether it's a delinquency view, an exposure metric, a covenant threshold, or a borrower segmentation. Consistency matters.

Without that discipline, reporting can become technically correct in one place and not in another. It gets harder to explain a trend change, harder to audit, harder to trust. With GitHub, we move toward a model where logic is centralized, changes are reviewed, work is traceable, accountability is clearer, and collaboration is more structured. That's the real value — not code management for its own sake, but better operational discipline for a team where several people touch the same numbers.

This also matters for teammates who are still mostly in Teradata, SQL, and Tableau day to day — that's not a problem, those tools stay valuable. The point isn't that everyone adopts the exact same workflow overnight; it's that there's one shared layer of governance behind the logic, so when someone moves teams or a definition needs to be explained six months later, the history is there.

I also want to be upfront about something: this doesn't pay off on day one. There's a chart on the page that shows the pattern we'd expect — hover across it or use the arrow keys, there's a table view below it too if you'd rather see the raw numbers.

*(Give the room a moment to look at the chart, then narrate it.)*

In the first few weeks, the GitHub line actually sits above the status quo — that's the learning curve. The team is getting comfortable with branch naming, review habits, and where logic now lives, and that takes a bit more time than just editing a query in place. Around week five, the lines cross. After that, the gap keeps widening: less time spent reconciling conflicting numbers, less time re-explaining a metric, faster handoffs when someone is out. The illustrative numbers on the page land around eighteen hours a cycle under the status quo versus roughly eight once the team is comfortable — the exact hours aren't the point, the shape is: a short dip, then a compounding payoff.”

### 4) Our current workflow (10:00–12:30)

“Now let's walk through the workflow itself — the 'How our team works today' section.

It starts in JupyterHub, where analysis, experimentation, and prototyping happen — notebooks, data exploration, testing assumptions, refining the logic. From there it moves into Python and PySpark, where we build reproducible data processing and transformation logic. We review and manage that logic in GitHub — an important step, because it makes the change visible, approved, and aligned with the team's standards before it goes anywhere else.

Once approved, the code moves through CI/CD and gets automated through Airflow, which is how the logic is scheduled and executed in controlled environments. The output then flows into Tableau, where it's consumed by broader stakeholders.

Explore, build, validate, review, deploy, report — that's the lifecycle. The thing to emphasize is that we're not operating in silos; the logic is connected across tools and governed by a clearer process end to end.”

### 5) Branching strategy and governance (12:30–15:30)

“Let's look at how that review step is actually structured — the branching model on the page.

We have a `master` branch, which is the production code path. It's connected to the production Airflow environment and protected — we don't make direct changes to production without a formal review.

We have a `staging` branch, the pre-production environment where validation happens before changes are promoted, connected to staging Airflow so the team can safely test the impact of a change.

And we have feature branches — short-lived, project-based branches for development work, named by project or workstream rather than by person: `portfolio-risk-refresh`, `covenant-data-fix`, `exposure-logic-update`.

The key governance principle is that production code isn't associated with an individual developer — it's associated with the project and the business domain. That gives us better traceability and shared accountability, and it means a change has to be reviewed before it moves into a higher-risk environment.”

### 6) GitHub commands in practice (15:30–18:30)

“Let's make this tangible with the command lab on the page — click through each one as I talk, and watch the diagram above the terminal. It shows your local machine on one side and GitHub on the other, and it animates which way things actually move for each command.

The flow looks like this: clone the repository, pull the latest from staging, create a branch, check status, commit with a clear message, push, open a pull request, and — once approved — merge.

- `git clone https://github.com/your-org/loan-portfolio-reporting.git` — watch the diagram: everything flows from GitHub down to your local machine.
- `git checkout staging && git pull origin staging` — same direction, remote to local, just syncing you up before you start new work.
- `git checkout -b portfolio-risk-refresh` — nothing moves across the wire here. The new branch only exists on your machine until you push it.
- `git status` — still entirely local; this is just you checking what you've changed before committing.
- `git add ... && git commit -m "Update delinquency logic for commercial portfolio"` — a new commit appears on your local side only. GitHub doesn't know about it yet.
- `git push origin portfolio-risk-refresh` — now the diagram flips direction: your local commit travels to GitHub for the first time.
- open a pull request into staging — the diagram shows a review gate sitting between local and remote. Nothing merges until someone approves it.
- `git merge` into staging, then into `master` once it's proven out — the approved change lands on the shared branch.

The point isn't that everyone becomes a Git expert overnight. It's that the team follows a consistent path: start from a single source of truth, isolate changes in a branch, review the work, validate before moving forward, and merge through a controlled process. The diagram is really just a visual reminder of one thing — most of what you do locally stays local until you deliberately push it, and nothing reaches production without going through that review gate.”

### 7) Onboarding, closing, and Q&A transition (18:30–20:00)

“Two last things, and then I'll hand it over to you.

First, onboarding. New teammates access JupyterHub, connect to the right workspace, pull the repository, and follow the same branch and review conventions as everyone else. There's a checklist on the page you can check off live if you're still working through it — it's saved on your device, so you can pick it back up later. Standard onboarding like this reduces drift between environments, which means fewer surprises in the numbers down the line.

Second, the summary. The value of GitHub for our team isn't just technical — it's operational, governance, and knowledge-sharing. It helps us manage logic consistently, improve visibility into changes, strengthen accountability, reduce the risk of inconsistent reporting, and support a more controlled path from staging into production. And it makes onboarding easier for colleagues who are already using it and for those still learning it — we're not saying everyone has to adopt the same stack the same way, just that there's value in a shared discipline around how logic is created, reviewed, and governed.

That's the message I want to leave you with. Let's open it up — I'd welcome thoughts on how this lands for teammates who are already onboarded and those who are still getting started.”

## Suggested closing line

“GitHub is not just a code repository. It is a practical framework for consistent logic, better traceability, and stronger governance within our internal reporting environment.”

## Q&A prompts

- How do you see this applying to teammates who still rely more on SQL and Tableau?
- What is the main operational benefit for colleagues who are not writing code daily?
- How do we balance flexibility with governance within our team?
- What are the biggest onboarding barriers for people who are new to GitHub?
- Where do you think this model could be expanded next within our team?
