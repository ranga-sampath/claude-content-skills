# Claude Content Skills

A collection of Claude Code skills for writing and content work.

## Available Skills

| Skill | Description | Type | Status |
| :--- | :--- | :--- | :--- |
| **humanize** | Rewrites a blog post, article, or social post to remove LLM writing fingerprints. Applies 22 humanization principles in a single pass and reports every change made, grouped by principle. | Operational | ![Verified](https://img.shields.io/badge/Status-Verified-success?style=flat-square) |

---

## Repository Structure

```
.
└── /humanize                            # Operational skill: remove LLM writing fingerprints
    ├── .claude/skills/humanize/
    │   └── skill.md                     # Skill definition + 22 humanization principles
    ├── docs/
    │   ├── overview.md                  # Architecture, principle summary, design decisions
    │   ├── how_to_use.md                # Installation, usage, workflow tips, troubleshooting
    │   └── test_plan.md                 # Test scenarios and verification approach
    ├── examples/
    │   ├── sample-llm-draft.md          # Sample input: blog post with seeded LLM fingerprints
    │   ├── sample-humanized-draft.md    # Reference output: the humanized version
    │   └── sample-humanize-report.md    # Reference output: the change report
    ├── how-to-humanize-llm-writing.md   # The article this skill is based on
    ├── LICENSE
    └── README.md
```
