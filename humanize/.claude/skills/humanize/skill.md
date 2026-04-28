# humanize — Claude Code Skill

## Description

Takes a blog post, article, LinkedIn post, X post, or any written document and rewrites it to remove LLM writing fingerprints. Applies a consistent set of humanization principles: removing em dashes, breaking parallel constructions, restoring first-person voice, adding contractions where natural, scoping universal claims, cutting redundant restatements, and more. The result reads like a person wrote it, not a model.

## When to Use

Invoke when the user:
- Provides a document and asks to "humanize it", "make it sound less like AI", or "remove the LLM voice"
- Wants a post or article cleaned up after AI-assisted drafting
- Uses `/humanize` explicitly

## Invocation

```
/humanize <file>
```

Where `<file>` is the path to the document to humanize.

---

## Execution Steps

### Step 1 — Parse Arguments

Extract from the invocation:
- `FILE`: required — path to the document to humanize

If no file path is provided, respond with:
```
Usage: /humanize <file>

Example: /humanize brand-journey/post-1.md

Accepts: markdown files, plain text files, or any readable document.
```
Stop here.

### Step 2 — Pre-flight Check

Verify the file exists:
```bash
test -f "<FILE>" && echo "OK" || echo "NOT_FOUND"
```
If NOT_FOUND: `Error: File not found: <FILE>` Stop.

Read the full file contents.

### Step 3 — Apply Humanization Principles

Work through the document applying every principle below. Make all changes in a single rewrite pass. Do not change the author's meaning, facts, named links, URLs, or overall structure. Only change phrasing, punctuation, and voice.

---

## Humanization Principles

### 1. Remove all em dashes
Em dashes are the most consistent LLM fingerprint. Replace every instance:
- Parenthetical em dashes (` — X — `) → commas or parentheses
- Connective em dashes introducing a clause → comma, colon, or period depending on context
- Em dashes before a list → colon
- Em dashes joining two independent clauses → period (split into two sentences)

**Examples:**
- `A short announcement — sitting in drafts — that I was...` → `A short announcement, sitting in my drafts, that I was...`
- `everything under one roof — writing, podcasts, links` → `everything under one roof: writing, podcasts, links`
- `Not dramatically — just quietly, honestly done.` → `Not dramatically. Just quietly, honestly done.`
- `about healthcare — it was about people` → `about healthcare. It was about people`

### 2. Break perfect parallel constructions
LLMs balance sentence pairs into matching shapes. Break the symmetry: let the second half be longer, more specific, or differently structured.

**Examples:**
- `Procedure produces coverage. Intent produces generalisation.` → `Procedure gives you coverage for what you've already seen. Intent gives you something to reason from when you haven't.`
- `Encode outcomes and you build X. Encode the structure and you build Y.` → `If you encode outcomes, you build X. If you encode the structure instead, you get Y.`

### 3. Collapse triple anaphora
Three consecutive sentences opening with the same phrase is an LLM rhetorical pattern. Merge into one sentence with a short closer.

**Example:**
- `It shows the timeline. It shows what you were thinking in 2020... It shows the arc.` → `It shows what you were thinking in 2020... The full arc, right there.`

### 4. Add contractions in declarations and formal-sounding sentences
LLMs use full forms ("This is", "That is", "It is", "cannot", "did not") even in casual passages. Add contractions where a person would naturally use them.

**Examples:**
- `This is the critical gap that linguistic gates cannot close.` → `That's the gap linguistic gates can't close.`
- `But here is something the five phases did not resolve.` → `But there's something these five phases didn't resolve.`

### 5. Restore first-person voice; remove passive constructions
When something personal happened, LLMs narrate it from a distance, making the thing the subject instead of the person.

**Examples:**
- `The podcast had never been started with a goal to become one of the best.` → `I had never set out to make one of the best podcasts in its category.`
- `The decision was made to...` → `I decided to...`

### 6. Add personal hedges to aphorisms and maxims
A naked declarative that sounds like a universal law reads as LLM-polished. Softening it with a personal hedge makes it sound earned.

**Examples:**
- `Every system prompt is a theory of what rules are for.` → `I've come to think every system prompt is a theory of what rules are for.`
- `Three things follow from this that hold across any domain:` → `A few things follow from this that I think hold in any domain.`

### 7. Scope universal claims down
LLMs expand the audience of a claim to its maximum possible scope. Narrow it to what the writer can actually vouch for.

**Example:**
- `Every AI builder faces this same choice.` → `Every builder writing a system prompt faces this choice.`

### 8. Replace tidy conclusions with honest uncertainty
If a resolution feels too clean for something genuinely complex, open it back up.

**Examples:**
- `That is an engineering problem.` → `It's harder than it sounds.`
- `It wasn't only that. It was a philosophical choice about what I was trying to build.` → `It was that, but it was also something bigger.`

### 9. Remove italics used as significance signals
If italics are marking "important terms" rather than indicating genuine stress or titles, remove them. Let the sentence carry the weight.

### 10. Merge staccato sentences that belong together
Three or four very short sentences for rhythmic effect should be merged or at least reduced.

**Examples:**
- `She had checked the rule. The rule was clear. She had done exactly what the protocol required.` → `She'd checked the rule, it was clear, she'd done exactly what the protocol required.`
- `I had already agreed to record with my next guest. He had said yes and we had a date on the calendar.` → `I had already agreed to record with my next guest and we had a date on the calendar.`

### 11. Cut redundant restatements
LLMs say something and then immediately restate it at higher resolution. Cut the first version or merge them.

**Examples:**
- `The feeling was surreal. It was, honestly, a feeling of being on top of the world.` → `Honestly, I felt like I was on top of the world.`
- `Through all of this — the quiet early period, the near-quit, the recognition — one thing anchored everything.` → `Through all of it, one thing anchored everything.`

### 12. Replace corporate prepositions and formal phrasing
Small vocabulary choices accumulate into an institutional register. Replace with natural equivalents.

**Examples:**
- `Post these episodes, the downloads picked up.` → `After those two episodes, the downloads picked up.`
- `Prior to launching, I...` → `Before I launched, I...`
- `In the context of this decision...` → `Given this decision...`

### 13. Replace nominalized emotion with direct expression
LLMs describe feelings by naming them from the outside. Express them directly.

**Examples:**
- `What I took from those two episodes was not about content or topics.` → `The lesson from those two episodes wasn't really about content or topics.`
- `It was a feeling of being on top of the world.` → `I felt like I was on top of the world.`

### 14. Simplify performative instruction closers
LLMs end with formal directives and checklists. Convert to a conversational sentence.

**Example:**
- `Before you ship... apply one check. Take any conclusion... Ask: could it have arrived...` → `Before you ship, try one thing: ask whether that conclusion could have arrived there the same way even if the answer was wrong.`

### 15. Cut meta-commentary transition phrases
LLMs narrate their own structure: "It is worth noting that," "It is important to understand that," "Having established X, we can now turn to Y," "With that in mind." These don't advance the argument; they announce that it's about to advance. Cut them and say the next thing directly.

**Examples:**
- `It is worth noting that the timing here matters.` → `The timing matters.`
- `It is important to understand that this was not a planned decision.` → `This wasn't a planned decision.`
- `With that in mind, let us consider how this applies to system prompts.` → `The same logic applies to system prompts.`
- `Having established the problem, we can now turn to solutions.` → *(just start the next paragraph)*

### 16. Remove importance-signaling adverbs
"Importantly," "Notably," "Interestingly," "Crucially," "Significantly" tell the reader what to find interesting instead of trusting the content to do it. Remove every instance.

**Examples:**
- `Notably, the downloads picked up after that episode.` → `The downloads picked up after that episode.`
- `Crucially, the route table is computed state, not configured state.` → `The route table is computed state, not configured state.`
- `Interestingly, the most successful episode came right after I had nearly quit.` → `The most successful episode came right after I had nearly quit.`

### 17. Remove intensifier openers
"At its core," "The reality is," "Fundamentally," "What this really means is" add words before the actual sentence without contributing meaning.

**Examples:**
- `At its core, this is a question about trust.` → `This is a question about trust.`
- `The reality is that most system prompts are written as lists of rules.` → `Most system prompts are written as lists of rules.`
- `Fundamentally, the problem is that we're encoding outcomes instead of structure.` → `The problem is that we're encoding outcomes instead of structure.`

### 18. Cut "in other words" restatements
LLMs restate a clear sentence in different words and signal it with "in other words." If the restatement adds nothing, cut it. If it genuinely simplifies, keep the simpler version and drop the original.

**Examples:**
- `The route was correct but the traffic was still blocked. In other words, routing wasn't the issue.` → `The route was correct but the traffic was still blocked. Routing wasn't the issue.`
- `The system prompt describes what to do, not why. In other words, it encodes procedure, not principle.` → `The system prompt describes what to do, not why. Procedure, not principle.`

### 19. Replace thesaurus vocabulary with plain words
LLMs reach for the more sophisticated synonym. Use the simpler word: "facilitate" → "help," "leverage" → "use," "demonstrate" → "show," "endeavour" → "try," "optimal" → "best," "utilise" → "use."

**Examples:**
- `This will facilitate a better understanding of the problem.` → `This will help you understand the problem.`
- `We need to leverage the existing infrastructure.` → `We can use what's already there.`
- `The results demonstrate a clear pattern.` → `The results show a clear pattern.`
- `This endeavour requires patience.` → `This takes patience.`

### 20. Cut explicit lesson extraction
LLMs name the takeaway at the end of every anecdote: "What this tells us is," "The lesson here is," "What emerges from this is." State the conclusion directly without announcing that you're stating it.

**Examples:**
- `What this tells us is that the timing mattered as much as the content.` → `The timing mattered as much as the content.`
- `The lesson here is that long shots are worth taking when your foundation is real.` → `Long shots are worth taking when your foundation is real.`
- `What emerges from this is a clear principle: start before you need it.` → `Start before you need it.`

### 21. Remove forward-signaling sentences
"What follows is," "The question then becomes," "This raises a further question" preview content that is about to arrive anyway. Cut them.

**Examples:**
- `What follows is a breakdown of the three key decisions I made during this period.` → `Three decisions defined this period.`
- `The question then becomes: how do we encode this distinction in a system prompt?` → `How do you encode this distinction in a system prompt?`
- `This raises a further question: what happens when the model is confident and wrong?` → `What happens when the model is confident and wrong?`

### 22. Interrogate "not just X, but Y" elevation
LLMs reflexively reframe every concrete problem as something deeper: "not just a technical problem, but a philosophical one." When the elevation is earned, name the deeper thing directly. When it isn't, drop the construction entirely.

**Examples:**
- `This is not just a technical problem, it is a philosophical one.` → `The technical problem was real. But underneath it was something harder to name.`
- `The challenge here is not just about routing, but about how we reason about state.` → `Routing was the surface problem. The deeper one was how we reason about state.`

---

## Step 4 — Write the Rewritten File

Overwrite the original file with the humanized version using the Edit or Write tool.

## Step 5 — Report Changes

After writing the file, list every change made, grouped by principle. Use this format for each change:

```
**[Principle name]**
- Before: `original text`
- After: `revised text`
- Why: one-sentence reason
```

Group changes under their principle heading. If multiple changes fall under the same principle, list them all under that heading before moving to the next.

Keep the list tight. Do not pad with commentary about overall quality or what was preserved unchanged.
