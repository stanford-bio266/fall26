# How to edit the course website

You can make every change on github.com in your browser. Nothing needs installing. After you save, the website updates by itself in about 2 minutes.

## Making a change

1. Open the repository on github.com.
2. Click the folder, then the file you want to change (see the table below).
3. Click the **pencil icon** (top right of the file) to edit.
4. Make your changes. The **Preview** tab shows roughly how it will look.
5. Click the green **Commit changes** button, then **Commit changes** again in the box that appears.
6. Wait about 2 minutes and refresh the website.

## Where things are

| What you want to change | File to open |
|---|---|
| Readings, instructions, or agenda for a class | `part-1` … `part-5` folder → `class-NN.md` (e.g. `part-4/class-15.md`) |
| A class date, title, guest, or "due" box | Same class file, the settings block at the top |
| The schedule page | Nothing to do: it updates automatically from the class files |
| Home page (office hours, key dates) | `index.md` |
| Reaction paper instructions | `assignments/reaction-papers.md` |
| Final paper instructions and topics | `assignments/final-paper.md` |
| Suggested readings for reaction papers | `assignments/suggested-readings.md` |
| Grading, AI policy, books, accessibility | `course-info` folder |

**Placeholders:** places waiting for content say *To be added.* Replace that line with your text. You can search the whole repository for "To be added" using the search box at the top of GitHub.

## The settings block at the top of each class file

```
---
nav_order: 14
title: "Market Failures"
date: "Thu 5 Nov"
guest: ""
due: ""
note: "No class Tue 3 Nov (Democracy Day)."
---
```

- Change only the text **inside the quotes**. Keep the quotes, and keep the two `---` lines.
- `guest`, `due`, and `note` are optional: leave them as `""` when there is nothing to show.
- Anything in `due` shows as a red box on the class page and in the schedule. Example: `due: "Second reaction paper"`.
- Text after a `#` on these lines is just an explanation. You can leave it or delete it.

## Writing the page text

The rest of the file is ordinary text with a few simple marks:

| You type | It shows |
|---|---|
| `## Before class` | a section heading |
| `**bold**` | **bold** |
| `*italic*` | *italic* |
| `[Text to show](https://link)` | a link |
| `1. ` at the start of a line | a numbered item |
| `- ` at the start of a line | a bullet point |
| `> **Note:** text` | a highlighted note box |

### Adding a reading

Copy an existing reading (both lines) and change the details:

```
3. **[Title of the reading](https://paste-the-link-here)**. Author. *Journal*, year. (5 pages)
   - Read pp. 1–10.
```

- The second line is the "how to read it" instruction. It must start with **three spaces** then `- `. You can delete it if there is no instruction.
- Numbering does not need to be perfect: the site renumbers lists automatically.

### Removing a reading

Delete its line(s).

## Adding a new class

1. Open `_templates/new-class.md` and copy everything.
2. Go into the right part folder (e.g. `part-4`), click **Add file → Create new file**.
3. Name it `class-21.md` (with the class number), paste, and fill it in.
4. Commit. It appears automatically in the sidebar, the Part page, and the schedule.

## Please don't change

- Files and folders starting with `_` (`_config.yml`, `_layouts`, `_sass`, `_templates`) and the `parts` folder. These control the design, not the content.
- Lines starting with `{:` and the "On this page" blocks on some pages. These are layout instructions.

## If something looks wrong

- Open the **Actions** tab on GitHub. A red ✗ means the last change has a problem. The most common cause is a missing quote mark or `---` line in a settings block.
- To undo a change: open the file, click **History**, open the previous version, and copy its text back.
