# How to Use: humanize Skill

## Installation

### 1. Clone the skills library

```bash
git clone https://github.com/ranga-sampath/claude-content-skills
cd claude-content-skills/humanize
```

### 2. Install the skill globally in Claude Code

Claude Code discovers skills from `~/.claude/skills/` — your global skills directory. Copying the file there registers the skill for every Claude Code session on this machine, regardless of which project directory you are working in.

```bash
mkdir -p ~/.claude/skills/humanize
cp .claude/skills/humanize/skill.md ~/.claude/skills/humanize/
```

### 3. Verify the skill is available

Open Claude Code and type `/` — `humanize` should appear in the autocomplete list.

---

## Usage

```
/humanize <file>
```

The file can be a markdown file, plain text file, or any readable document. Relative and absolute paths are both accepted.

### Examples

```bash
# Humanize a blog post draft
/humanize drafts/post-june.md

# Humanize a LinkedIn post
/humanize posts/linkedin-june-4.md

# Humanize using an absolute path
/humanize /Users/you/writing/article.md
```

Claude will:
1. Verify the file exists
2. Read the full contents
3. Apply all 22 humanization principles in a single rewrite pass
4. Overwrite the original file with the humanized version
5. Print a change report grouped by principle

---

## What the Change Report Covers

After rewriting, the skill prints every change made:

| Section | Content |
|---|---|
| **Principle heading** | The name of the principle applied |
| **Before** | The original phrase or sentence |
| **After** | The humanized replacement |
| **Why** | One-sentence reason for the change |

Only changes are listed. Unchanged passages are not mentioned.

See `examples/sample-humanize-report.md` for a reference output.

---

## Reviewing Changes

Because the skill rewrites the file in place, use `git diff` to see exactly what changed:

```bash
git diff drafts/post-june.md
```

If a change is wrong, revert it directly in the file. The change report tells you which principle triggered it, so you can find the passage quickly.

---

## Workflow Tip: Detect First, Then Humanize

Before humanizing, run `/detect-llm-writer` to get a confidence score and see which principles have the highest presence in the document. That tells you where the fingerprint is heaviest before you commit to a rewrite.

```bash
# Step 1 — score the document
/detect-llm-writer drafts/post-june.md

# Step 2 — humanize it
/humanize drafts/post-june.md

# Step 3 — review changes
git diff drafts/post-june.md
```

---

## Troubleshooting

| Problem | Solution |
|---|---|
| `Usage: /humanize <file>` error | Provide a file path: `/humanize path/to/file.md` |
| `Error: File not found` | Check the path; try an absolute path |
| `/humanize` not in autocomplete | Confirm `~/.claude/skills/humanize/skill.md` exists; restart Claude Code |
| Change report is empty | The document may already be mostly human-written; check with `/detect-llm-writer` first |
| A change broke the meaning | Revert the specific sentence in the file; the change report identifies which principle triggered it |
