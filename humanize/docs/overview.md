# Overview: humanize — Claude Code Skill

## What This Skill Is

An **operational Claude Code skill** — invoked via `/humanize` — that reads a blog post, article, LinkedIn post, X post, or any written document and rewrites it to remove LLM writing fingerprints. Applies 22 humanization principles in a single rewrite pass. The result reads like a person wrote it, not a model.

## The Problem It Solves

LLM-assisted writing has a recognizable voice. Once you learn it, you can't stop hearing it. The sentences balance too perfectly. The conclusions arrive on time. The structure is complete and clean in a way that most good human writing isn't. Em dashes appear every few sentences. Every paragraph earns its place. Nothing is wasted, nothing half-formed.

This skill removes those fingerprints. It preserves the author's meaning, facts, structure, URLs, and named references — only phrasing, punctuation, and voice change.

## Architecture: Two Stages

```
Document (.md, .txt, or any plain-text file)
    │
    ▼
[Stage 1] Validate
    │  Check file path provided, file exists, read contents
    ▼
[Stage 2] Rewrite + Report  (Claude Code — native)
       Applies all 22 humanization principles in a single pass
       Writes humanized version back to the original file
       Reports every change made, grouped by principle
```

Both stages run natively inside Claude Code. No parser script. No external API key. No pip installs.

## The 22 Humanization Principles

| # | Principle | What it targets |
|---|---|---|
| 1 | Remove all em dashes | The most consistent LLM fingerprint; replace with comma, colon, or period |
| 2 | Break perfect parallel constructions | Matched sentence pairs that read as composed, not thought |
| 3 | Collapse triple anaphora | Three consecutive sentences opening with the same phrase |
| 4 | Add contractions in declarations | "It is" / "cannot" / "did not" in casual passages |
| 5 | Restore first-person voice | Passive narration of personal events |
| 6 | Add personal hedges to aphorisms | Naked maxims that read as universal laws |
| 7 | Scope universal claims down | "Every AI builder" → "every builder writing a system prompt" |
| 8 | Replace tidy conclusions with honest uncertainty | Resolutions too clean for genuinely complex problems |
| 9 | Remove italics as significance signals | Italicized "important terms" rather than genuine stress |
| 10 | Merge staccato sentences | Three-four short sentences for rhythmic effect |
| 11 | Cut redundant restatements | A thought stated and then immediately restated at higher resolution |
| 12 | Replace corporate prepositions | "Prior to", "post", "in the context of", "utilise" |
| 13 | Replace nominalized emotion | "A feeling of" / "a sense of" instead of direct expression |
| 14 | Simplify performative instruction closers | Checklisted directives at the end of a piece |
| 15 | Cut meta-commentary transition phrases | "It is worth noting that", "Having established X, we now turn to" |
| 16 | Remove importance-signaling adverbs | "Importantly", "Notably", "Crucially", "Interestingly" |
| 17 | Remove intensifier openers | "At its core", "The reality is", "Fundamentally" |
| 18 | Cut "in other words" restatements | Restating a clear sentence with a "softer" version |
| 19 | Replace thesaurus vocabulary | "Facilitate" → "help", "leverage" → "use", "demonstrate" → "show" |
| 20 | Cut explicit lesson extraction | "What this tells us is", "The lesson here is" |
| 21 | Remove forward-signaling sentences | "What follows is", "The question then becomes" |
| 22 | Interrogate "not just X, but Y" elevation | Reflexive reframing of every concrete problem as something deeper |

## Design Decisions

| Decision | Choice | Reason |
|---|---|---|
| Rewrite in place | Overwrites original file | Author works on one file; `git diff` shows exactly what changed; no file clutter |
| Single pass | One rewrite, not iterative | Multiple passes risk over-editing; one thorough pass is enough |
| Change report | Grouped by principle | Lets the author verify and selectively revert individual changes |
| No Python parser | None needed | Humanization is qualitative judgment, not rule-based extraction |
| AI-native | Claude Code — no external calls | Claude IS the analyst; no separate API key required |

## What This Skill Intentionally Omits

| Omitted | Why |
|---|---|
| Spell checking | Use your editor's built-in spellchecker |
| Fact checking | Skill changes voice, not content |
| Restructuring | No section reordering; no ideas added or removed |
| Tone shifting | Preserves the author's register; only removes LLM-specific patterns |
| HTML / rich text | Operates on markdown and plain text files |
| Detection scoring | Use the companion `detect-llm-writer` skill for a confidence score before humanizing |
