# Test Plan: humanize Skill

## Test Fixtures

| Fixture | Description | Key Patterns to Verify |
|---|---|---|
| `examples/sample-llm-draft.md` | ~400-word blog post draft with 13 LLM fingerprints across 9 principles | Em dashes (×2), importance-signaling adverbs (×2), intensifier openers (×2), meta-commentary transitions (×2), parallel construction, corporate preposition, explicit lesson extraction, first-person voice suppression, thesaurus vocabulary |

---

## Test Scenarios

### T1 — Standard rewrite (sample fixture)

```
/humanize examples/sample-llm-draft.md
```

**Expected:**
- File overwritten with humanized version
- Change report printed, grouped by principle
- All 13 seeded fingerprints removed or corrected
- Author's meaning, structure, and facts unchanged
- Compare output against `examples/sample-humanized-draft.md` as reference

**Key things to check:**
- Em dash in opening sentence replaced with period
- "Importantly" and "Notably" removed
- "Prior to" → "Before I"
- "At its core" → removed
- "The reality is that" → stripped
- "What this tells us is that" → cut
- "leverage" → "use"
- Contractions added throughout

---

### T2 — LinkedIn post (short-form)

Create a short LinkedIn post draft (~150 words) with em dashes, parallel constructions, and importance-signaling adverbs. Run `/humanize` on it.

**Expected:**
- Shorter document handled correctly
- No over-editing of content that is already natural
- Change report is proportionally shorter

---

### T3 — Document that is already mostly human-written

Use a piece of writing with minimal LLM fingerprints (few or no em dashes, natural contractions, scoped claims).

**Expected:**
- File written back with minimal changes
- Change report is short or empty
- No false positives (natural parallel constructions left alone, deliberate em dashes flagged but not over-removed)

---

### T4 — Markdown with URLs, code blocks, and formatting

Use a document containing inline URLs, fenced code blocks, and bold/italic formatting.

**Expected:**
- URLs unchanged
- Code blocks unchanged (skill should not rewrite code)
- Bold/italic formatting preserved where not used as significance signals
- Only prose sections rewritten

---

### T5 — Error: no argument

```
/humanize
```

**Expected:**
```
Usage: /humanize <file>

Example: /humanize brand-journey/post-1.md

Accepts: markdown files, plain text files, or any readable document.
```

---

### T6 — Error: file not found

```
/humanize /tmp/does-not-exist.md
```

**Expected:** `Error: File not found: /tmp/does-not-exist.md`

---

## Verification Approach

Unlike parser-based skills, there is no deterministic ground truth for humanization output — the rewrite involves judgment. Verification is qualitative:

1. **Seeded fingerprints removed:** Check that all known LLM patterns in the test fixture were addressed.
2. **Meaning preserved:** Read the humanized version and confirm no facts, named references, or structural decisions changed.
3. **Change report accuracy:** Every item in the report should correspond to an actual change in the file. No phantom changes.
4. **No over-editing:** The humanized version should read naturally — not stripped of all rhythm, just stripped of LLM-specific patterns.
