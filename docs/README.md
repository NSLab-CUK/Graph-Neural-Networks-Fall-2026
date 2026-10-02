# Course Website — Maintainer Guide

This folder is the course website, built with [Jekyll](https://jekyllrb.com/) and published by GitHub Pages:

**https://nslab-cuk.github.io/Graph-Neural-Networks-Fall-2026/**

GitHub Pages serves `main` from the `/docs` folder. Every push to `main` that changes something in `docs/` rebuilds the site automatically, usually within a minute or two. There is nothing to deploy by hand.

## Weekly update

Do this each week after the notebooks are pushed to `W<N>/`.

### 1. Add the lecture

Copy the latest file in `_lectures/` (for example, `w05.md` → `w06.md`), then update the date, title, summary, and notebook paths. On the **Schedule** page, each lecture becomes a week card: a Tuesday lecture row, and a Thursday practice row (two days later) with the links whose name contains `practice`.

```yaml
---
type: lecture
date: 2026-10-06T10:00:00+09:00      # Tuesday of that week
title: "Week 6: Attentive GNNs and Graph Pooling"
tldr: "GAT, attention in heterogeneous graphs, DiffPool and SAGPool."
links:
    - url: https://github.com/NSLab-CUK/Graph-Neural-Networks-Fall-2026/blob/main/W6/SampleCode_6.ipynb
      name: sample code
    - url: https://colab.research.google.com/github/NSLab-CUK/Graph-Neural-Networks-Fall-2026/blob/main/W6/SampleCode_6.ipynb
      name: sample code (Colab)
    - url: https://github.com/NSLab-CUK/Graph-Neural-Networks-Fall-2026/blob/main/W6/PracticeCode_6.ipynb
      name: practice
    - url: https://colab.research.google.com/github/NSLab-CUK/Graph-Neural-Networks-Fall-2026/blob/main/W6/PracticeCode_6.ipynb
      name: practice (Colab)
---
```

If the practice session moves to a different day that week (for example, because of a holiday), add `practice_date: 2026-10-09` to the lecture's front matter.

### 2. Add the assignment

Copy the latest file in `_assignments/` (for example, `a05.md` → `a06.md`). Set `date` to the Thursday it is released and the due date to the following Wednesday:

```yaml
---
type: assignment
date: 2026-10-08T11:00:00+09:00      # Thursday release
title: "Assignment #6: <short title>"
links:
    - url: https://github.com/NSLab-CUK/Graph-Neural-Networks-Fall-2026/blob/main/W6/Assignment_6.ipynb
      name: notebook
    - url: https://colab.research.google.com/github/NSLab-CUK/Graph-Neural-Networks-Fall-2026/blob/main/W6/Assignment_6.ipynb
      name: notebook (Colab)
due_event:
    type: due
    date: 2026-10-14T23:59:00+09:00  # following Wednesday
    description: "Assignment #6 due"
---
**Tasks**

1. ...
2. ...
```

### 3. Add the solution after the deadline

Add one line to the assignment's front matter:

```yaml
solutions: https://github.com/NSLab-CUK/Graph-Neural-Networks-Fall-2026/blob/main/W6/Solution_6.ipynb
```

### 4. Commit and push to `main`

### Tips

- Keep two-digit filenames (`w06`, `w10`, `a06`, `a10`) so files stay in order.
- An assignment is listed under a week on the Schedule page when its release `date` falls within 7 days of that week's lecture.
- Always include the `+09:00` (KST) timezone in dates.
- A Colab link is the GitHub link with `https://github.com/` replaced by `https://colab.research.google.com/github/`.

## Where things live

| To change… | Edit |
|---|---|
| Staff names, photos, links | `_data/people.yml` (photos go in `_images/pp/`) |
| Course plan (week-by-week topics) | `plan.md` |
| Home page text, grading, contacts | `index.md` |
| Submission and late policy (shown on every assignment page) | `_data/late_policy.yml` |
| Class days and periods (weekly timetable) | `_data/schedule.yml`, plus the intro sentence in `schedule.md` and the "Weekly Routine" list in `index.md` |
| Menu tabs | `_data/nav.yml` |
| Previous years' links | `_data/previous_offering.yml` |
| Course name, semester, course code, site URL | `_config.yml` |
| Theme colors | `_sass/_user_vars.scss` |
| Header and footer | `_includes/header.html`, `_includes/footer.html`, `_sass/_header.scss`, `_sass/_footer.scss` |
| Slides and PDFs | Put them in `static_files/` and link them as `/static_files/<name>.pdf` |

Links in front matter can be absolute (`https://...`) or site-relative (`/static_files/...`). Site-relative links get the `/Graph-Neural-Networks-Fall-2026` prefix added automatically.

## Previewing locally (optional)

You need Ruby with Jekyll installed. On Windows, first install timezone data once:

```
gem install tzinfo-data
```

Then, from this `docs/` folder:

```
jekyll serve
```

Open http://localhost:4000/Graph-Neural-Networks-Fall-2026/. The page reloads when you save a file. Changes to `_config.yml` need a restart.

## Setting up next year's site

1. Create the new repository (for example, `Graph-Neural-Networks-Fall-2027`) and copy this `docs/` folder into it.
2. In `_config.yml`, update `baseurl`, `course_semester`, and `github_repo`.
3. Delete the files in `_lectures/` and `_assignments/`. If the class days or periods change, update `_data/schedule.yml`.
4. Add this year to the top of `_data/previous_offering.yml`.
5. Update `_data/people.yml` and `plan.md`.
6. In the repository's **Settings → Pages**, choose **Deploy from a branch**, then `main` and `/docs`.

---

Based on [kazemnejad/jekyll-course-website-template](https://github.com/kazemnejad/jekyll-course-website-template) (MIT license, see `LICENSE`).
