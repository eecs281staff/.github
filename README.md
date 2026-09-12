# EECS 281 Staff Hub

Orientation for course staff of **EECS 281: Data Structures and Algorithms**
(University of Michigan). This repo is the front door to the `eecs281staff`
org: what exists, where it lives, what it's built with, and the conventions
that keep ~35 repos coherent.

## Where everything lives

The org is organized as a **workspace**: one meta-repo,
[`eecs281staff/eecs281`](https://github.com/eecs281staff/eecs281), declares
every course repo in a `workspace.yaml` manifest and clones them as child
directories. To get the whole course on disk:

```bash
git clone git@github.com:eecs281staff/eecs281.git
cd eecs281
bin/sync
```

| Area | Repos | What's there |
|---|---|---|
| Website | `eecs281.org` | The public course site |
| Projects | `p0-statistics` … `p4-zoo` (19 repos) | Specs, autograders, solutions per project |
| Labs | `l00-template` … `l10-deals-on-meals` | Quizzes, starter code, slides per lab |
| Sample code | `wordcount-demo`, `search-demo`, `nqueens-demo` | Small demos shown in lecture |
| Software | `Makefile`, `official-score`, `xcode_redirect`, `exam-starter-code-distributor` | Student-facing tooling |
| Slides | `lecture-slides` | PowerPoint source for the lecture decks |
| Exams | `exam-authoring` | **Retired** — kept for reference |
| Org profile | `.github` (this repo) | Staff hub |

## Technologies

- **C++** with the course's advanced `Makefile` (debug/release/profile
  targets, submission tarballs). Students build with the same Makefile the
  repos carry.
- **GitHub Pages + Jekyll** for project/lab specs (primer-spec theme) and the
  course site; deploys run through GitHub Actions.
- **GitHub Actions** in content repos for the release rhythm: hide-solutions
  and release-solutions workflows keep answers out of student sight until
  their release date.
- **Gradescope** for submissions and autograding.
- **PowerPoint** for lecture decks; lecture capture flows through
  MiVideo/Kaltura, with slides and materials surfaced via Canvas.
- **Claude Code + workspace-toolkit** for staff workflow: the workspace
  manifest, `bin/sync` / `bin/status`, and the `/push` and `/audit` commands.

## Scheduling

The course runs every semester; content turns over on a per-semester rhythm:

- Each semester selects its project lineup from the `p0`–`p4` pools (one repo
  per project variant; repos are reused across semesters, not forked).
- Labs are shared infrastructure, reworked as needed (most recently
  overhauled August 2026).
- *(Fill in: current-semester assignments, exam dates, and the staff
  calendar link.)*

## Conventions

1. **Repo naming**: `p<phase>-<slug>` for projects, `l<number>-<slug>` for
   labs. The workspace manifest is the authoritative list.
2. **Private by default.** Content repos stay private; only deliberately
   public things (sample code, the website, student tooling) are public.
   Solutions ship to students only via the release workflows.
3. **Sensitive material stays out of repos entirely**: academic-integrity
   cases, plagiarism-tool output, credentials, and student data never enter
   the org.
4. **One repo, one concern.** Cross-repo coordination lives in the workspace
   repo's docs, not in content repos.

## Onboarding checklist

1. Get added to the `eecs281staff` GitHub org.
2. Clone the workspace and `bin/sync` (needs `git`, ssh access, `python3`
   with PyYAML).
3. Read `AGENTS.md` in the workspace root — the working rules — and skim
   `workspace.yaml` to learn the map.
