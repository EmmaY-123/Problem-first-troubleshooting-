---
name: problem-first-troubleshooting
description: Problem-first troubleshooting workflow for unexpected errors, failed commands, broken previews/renders, missing files, permission issues, tool limitations, confusing output, or any situation where Codex is tempted to switch methods or use a workaround. Use to pause, explain the exact problem and likely cause, offer the simplest fix first, and ask before changing file structure, workflow, tools, or approach.
---

# Problem-First Troubleshooting

Use this skill when work hits an unexpected problem and a workaround is possible. The goal is to keep the user oriented and avoid silently taking a more complex path.

## Required Workflow

Before switching methods, changing file structure, renaming files/folders, rewriting artifacts, or using a workaround:

1. State the exact problem plainly.
2. Explain the likely cause in simple terms.
3. Offer the simplest fix first.
4. Ask before switching methods if it affects the user's file structure, workflow, tool choice, or future maintenance.

## What Counts As A Problem

Use this workflow for issues such as:

- A command, tool, render, preview, or test fails.
- A file exists but cannot be read, written, linked, imported, or rendered.
- An output appears broken, missing, malformed, or different from expected.
- A path, filename, permission, environment, dependency, or app behavior is likely the cause.
- There are multiple possible fixes and one would alter the user's setup.
- A workaround would be faster for Codex but may be less clear for the user.

## Response Pattern

When the problem affects the user-visible workflow, say something like:

```text
I found the issue: [plain problem].
Likely cause: [short cause].
Simplest fix: [lowest-impact fix].
Other options: [only if useful].
Do you want me to try the simplest fix first?
```

For tiny internal hiccups that do not affect the user, continue normally. If the workaround is invisible, reversible, and does not change user files or workflow, a brief update is enough.

## Decision Rule

Prefer the fix that preserves the user's current structure and mental model. If changing the structure would solve the problem more cleanly, explain that clearly and ask first.

## Example

Problem: Markdown images do not render.

Good response:

```text
I found the issue: the image files exist, but the Markdown preview is not resolving the image links.
Likely cause: the folder path contains a space, which some Markdown renderers fail to parse inside image links.
Simplest fix: rename the folder to remove the space, or use a no-space asset folder path.
Do you want to rename the folder first before I try HTML embeds or other workarounds?
```

Avoid silently switching to a more complex method before explaining the root cause.
