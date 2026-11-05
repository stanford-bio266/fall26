# BIO 166/266 course site (Just the Docs)

**Editing content? See [EDITING-GUIDE.md](EDITING-GUIDE.md).**

A GitHub Pages site for *Securing against biological threats* (Stanford, Fall 2026), built with the [Just the Docs](https://just-the-docs.com) theme.

## Structure

| Path | What |
|---|---|
| `index.md` | Home: at-a-glance info, key dates, course map |
| `schedule.md` | Builds itself from the class files; no manual editing |
| `part-1/` … `part-5/` | One file per class (`class-NN.md`). Each folder is automatically placed under its Part in the sidebar |
| `parts/` | The five Part landing pages |
| `assignments/` | Reaction papers, final paper, suggested readings |
| `course-info/` | Goals & format, grading, books, accessibility, AI policy |
| `_templates/new-class.md` | Copy this to add a class |
| `_layouts/class.html` | Builds each class page's heading, date, guest and due box from its settings |
| `_config.yml` | Site settings, including `url` and `baseurl` |

## Publishing

In `_config.yml`, `url` must be `https://YOUR-USERNAME.github.io` and `baseurl` must be `/` plus the repository name (currently `/fall26`). GitHub Pages: Settings → Pages → Deploy from a branch → `main` / root.

## Local preview (optional)

```bash
bundle install
bundle exec jekyll serve
```
