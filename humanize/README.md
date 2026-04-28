# humanize — Claude Code Skill

A Claude Code skill that reads a blog post, article, LinkedIn post, X post, or any written document and rewrites it to remove LLM writing fingerprints.

## What It Does

Given any markdown or plain-text file, the skill:

1. **Reads** the full document
2. **Rewrites** it in a single pass, applying 22 humanization principles: removing em dashes, breaking parallel constructions, restoring first-person voice, adding contractions where natural, scoping universal claims, cutting redundant restatements, and more
3. **Reports** every change made, grouped by principle, so you can verify and selectively revert

The result reads like a person wrote it, not a model.

## Prerequisites

| Requirement | Notes |
|---|---|
| Claude Code | [Install guide](https://docs.anthropic.com/en/docs/claude-code) |

No Python. No external packages. No API key beyond Claude Code itself.

## Installation

```bash
# 1. Clone the skills library
git clone [repo-url]
cd [repo-name]/humanize

# 2. Copy to ~/.claude/skills/ — Claude Code discovers skills from this global directory,
#    making the skill available in every session regardless of working directory.
mkdir -p ~/.claude/skills/humanize
cp .claude/skills/humanize/skill.md ~/.claude/skills/humanize/
```

## Usage

```bash
/humanize <file>
```

### Examples

```bash
# Humanize a blog post draft
/humanize drafts/post-june.md

# Humanize a LinkedIn post
/humanize posts/linkedin-june-4.md
```

The skill rewrites the file in place. Use `git diff` to review what changed.

## Output

After rewriting, the skill prints a change report:

| Section | Content |
|---|---|
| **Principle heading** | The name of the principle applied |
| **Before** | The original phrase or sentence |
| **After** | The humanized replacement |
| **Why** | One-sentence reason for the change |

See `examples/sample-humanize-report.md` for a reference output.

## Repository Structure

```
humanize/
├── .claude/skills/humanize/
│   └── skill.md                    # Claude Code skill definition + 22 humanization principles
├── docs/
│   ├── overview.md                 # Architecture, principle summary, design decisions
│   ├── how_to_use.md               # Installation, usage, workflow tips, troubleshooting
│   └── test_plan.md                # Test scenarios and verification approach
├── examples/
│   ├── sample-llm-draft.md         # Sample input: blog post with seeded LLM fingerprints
│   ├── sample-humanized-draft.md   # Reference output: the humanized version
│   └── sample-humanize-report.md   # Reference output: the change report
├── how-to-humanize-llm-writing.md  # The article this skill is based on
└── README.md
```

## Related Skills

- `detect-llm-writer` — scores a document for LLM authorship likelihood across the same 22 patterns; run this first to see where the fingerprint is heaviest before humanizing. Available in the same repository.

## Background

This skill is based on the article **"How to Tell You're Reading an LLM (And How to Fix It)"** — included in this repository as `how-to-humanize-llm-writing.md`. The article documents all 22 patterns with before/after examples. The skill automates the same process.
