# Canvas Workflow

Use a repo-local `canvas.md` as a live visual display surface when working with a coding agent in VS Code Remote SSH or another remote workspace where direct image links are awkward.

The user keeps `canvas.md` open in Markdown Preview. When the agent generates a new plot/image, it refreshes `canvas.md` so the preview shows the latest visual.

## Canvas Format

Keep `canvas.md` minimal:

```markdown
![short alt text](relative/path/to/current_image.png)

Short concise figure caption.
```

Rules:

- Use a path relative to the repo/workspace root.
- Prefer a fresh image filename for each new figure to avoid preview image caching.
- Keep `canvas.md` nearly text-free.
- Do not accumulate old figures, links, source-file lists, headings, or explanatory text.
- Put interpretation and analysis in chat, not in `canvas.md`, unless the user asks otherwise.
- After refreshing `canvas.md`, tell the user the canvas has been refreshed.

## Agent Instructions

Copy or adapt this into a project instruction file such as `CLAUDE.md`, `AGENTS.md`, or a repo README:

```markdown
For quick plot/image display in remote workspaces, use a repo-local `canvas.md` as a live visual surface. When generating a plot or image for inspection, overwrite `canvas.md` with only the current image and, optionally, one concise caption:

![short alt text](relative/path/to/current_image.png)

Short concise figure caption.

Use repo-relative paths, prefer fresh image filenames to avoid preview caching, and keep interpretation in chat rather than in `canvas.md` unless asked otherwise.
```

## Starter Template

Copy [`canvas.md`](canvas.md) to the root of a working repo, then replace the image path and caption whenever a new figure should be displayed.
