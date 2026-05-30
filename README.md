[README.md](https://github.com/user-attachments/files/28415848/README.md)
# problem-first-troubleshooting

A Codex skill that enforces a **problem-first workflow** when unexpected errors, broken outputs, or workarounds arise. Instead of silently switching methods, Codex pauses to explain what went wrong, why, and what the simplest fix is — before taking any action that could affect your files or workflow.

---

## What It Does

When Codex hits a problem and a workaround is possible, this skill requires it to:

1. **State the exact problem** in plain language
2. **Explain the likely cause** simply
3. **Offer the simplest fix first**
4. **Ask before changing anything** — file structure, tools, workflow, or approach

---

## When It Triggers

- A command, tool, render, preview, or test fails
- A file exists but can't be read, written, linked, imported, or rendered
- Output appears broken, missing, malformed, or unexpected
- A path, permission, environment, or dependency is likely the cause
- Multiple fixes exist and one would alter your setup
- A workaround would be faster for Codex but less clear for you

---

## Response Format

```
I found the issue: [plain problem].
Likely cause: [short cause].
Simplest fix: [lowest-impact fix].
Other options: [only if useful].
Do you want me to try the simplest fix first?
```

---

## Example

**Problem:** Markdown images don't render.

**Codex response with this skill:**
```
I found the issue: the image files exist, but the Markdown preview is not resolving the image links.
Likely cause: the folder path contains a space, which some Markdown renderers fail to parse inside image links.
Simplest fix: rename the folder to remove the space, or use a no-space asset folder path.
Do you want to rename the folder first before I try HTML embeds or other workarounds?
```

---

## Why This Exists

Without this skill, Codex may silently take a more complex path — renaming files, restructuring folders, or switching tools — without explaining why. This skill keeps you oriented and in control, so nothing changes under the hood without your awareness.

---

## Installation

Place `SKILL.md` in your Codex skills directory:

```
~/.codex/skills/problem-first-troubleshooting/SKILL.md
```
