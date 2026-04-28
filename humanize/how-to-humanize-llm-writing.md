# How to Tell You're Reading an LLM (And How to Fix It)

There's a voice that AI writing has. Once you learn to hear it, you can't stop.

It's not that the writing is bad. It's that it's too clean. The sentences balance each other perfectly. The conclusions arrive on time. The important terms are italicized. Every paragraph earns its place. Nothing is wasted. No thought is half-formed.

That's the tell. People waste words. They circle back. They say something and then immediately realize they said it slightly wrong and say it again differently. LLMs don't do that. They compose.

I've been working through this problem with my own writing, going post by post and finding the places where the AI fingerprint is most visible. What I've found is twenty-two patterns that reliably give it away, with before-and-after examples for each. Some of these are mechanical. Others are about something harder to name, a kind of epistemic honesty that LLMs struggle to fake.

---

## 1. Em Dashes, Everywhere

This is the most consistent tell. LLMs reach for the em dash constantly. As a parenthetical, as a connective, as a way to add a clause that felt too long to fold into the sentence naturally. In a paragraph of a few hundred words, you might find four or five of them.

The fix is almost always one of three things: a comma, a colon, or a period. Pick the one that matches what the sentence is actually doing.

**Before:** `A short announcement — sitting in drafts — that I was going to wind down the podcast.`

**After:** `A short announcement, sitting in my drafts, that I was going to wind down the podcast.`

**Before:** `Not dramatically — just quietly, honestly done.`

**After:** `Not dramatically. Just quietly, honestly done.`

**Before:** `everything under one roof — writing, podcasts, links to every social handle.`

**After:** `everything under one roof: writing, podcasts, links to every social handle.`

Replace every em dash. There is almost never a case where it was the best choice.

---

## 2. Perfect Parallel Constructions

LLMs love symmetry. Give them two ideas and they'll balance them into matching sentence shapes. Give them three and you get a triptych. It reads as composed rather than thought.

The fix is to break the symmetry. Let the second half of the comparison be longer, more specific, or differently structured than the first. That's how thinking actually works when you're working something out rather than presenting a finished argument.

**Before:** `Procedure produces coverage. Intent produces generalisation.`

**After:** `Procedure gives you coverage for what you've already seen. Intent gives you something to reason from when you haven't.`

**Before:** `Encode outcomes and you build a narrow system. Encode the structure and you build something that generalises.`

**After:** `If you encode outcomes, you build a narrow system. If you encode the structure instead, you get something that can reason past what it's already seen.`

**Before:** `The 2013 incident asked whether... The system prompt journey asked whether...`

**After:** `The 2013 incident was about whether... What I was doing in 2026 was asking the same question of a machine.`

---

## 3. Triple Anaphora

A specific version of the parallel construction problem, worth calling out separately because it's so common. LLMs will open three consecutive sentences with the same phrase for rhetorical effect.

**Before:** `It shows the timeline. It shows what you were thinking about in 2020, what you were building in 2021, where you were headed in 2022. It shows the arc.`

**After:** `It shows what you were thinking about in 2020, what you were building in 2021, where you were headed in 2022. The full arc, right there.`

Collapse it. The repetition doesn't add weight; it signals that something generated it.

---

## 4. Contractions in Declarations

LLMs default to full forms even when the sentence is making a casual point. "This is the problem." "That is not how it works." "It is worth noting." The formality is slightly mismatched to the register of the surrounding prose, and the cumulative effect is a voice that sounds like it's being careful rather than just talking.

Add contractions where a person would naturally use them.

**Before:** `This is the critical gap that linguistic gates cannot close.`

**After:** `That's the gap linguistic gates can't close.`

**Before:** `But here is something the five phases did not resolve.`

**After:** `But there's something these five phases didn't resolve, and I want to be direct about it.`

The second example adds something the first doesn't: a signal that the writer knows this is uncomfortable to say. "I want to be direct about it" is a very human thing to put in writing.

---

## 5. Passive Voice and the Missing "I"

When something genuinely personal happened, LLMs often narrate it from a slight distance, letting the subject of the sentence be the thing rather than the person. This is grammatically fine but it creates a flatness in passages that should feel lived-in.

**Before:** `The podcast had never been started with a goal to become one of the best in its category.`

**After:** `I had never set out to make one of the best podcasts in its category.`

**Before:** `It took me five attempts to understand what I was actually building each time I fell short.`

**After:** `Each time I thought I was making progress, I wasn't yet seeing what I was actually building.`

The second example is more than just a voice change. The original says "I understood after five attempts." The revision says "I kept misreading my own progress." That's more honest, and more specific, which is what humanizing is really about.

---

## 6. Aphorisms Without a Source

LLMs love a crisp closing statement. Something that could be pulled out of context and put on a slide. The problem is that a maxim delivered without attribution sounds like a declaration, and declarations from a bylined writer invite skepticism. Where did you get that? Have you earned it?

A personal hedge changes the relationship. It's not a rule; it's something you've come to think.

**Before:** `Every system prompt is a theory of what rules are for.`

**After:** `I've come to think every system prompt is a theory of what rules are for.`

**Before:** `Three things follow from this that hold across any domain.`

**After:** `A few things follow from this that I think hold in any domain.`

The revision also does something else worth noting: "a few things" instead of "three things." Humans aren't always sure how many items are in a list when they start making it.

---

## 7. Universal Claims That Should Be Scoped

Related to the aphorism problem. LLMs expand the audience of a claim to its maximum possible scope by default. "Every AI builder." "Anyone working in this space." "All teams face this." A person who has actually been in the room tends to scope their claims more carefully, because they know where their experience runs out.

**Before:** `Every AI builder faces this same choice.`

**After:** `Every builder writing a system prompt faces this choice.`

Narrower is more credible. And usually more accurate.

---

## 8. Tidy Conclusions

LLMs resolve things. When something is complex or unresolved, they tend to name the complexity and then still resolve it. A human who's genuinely grappling with something doesn't always close the loop cleanly.

**Before:** `That is an engineering problem.`

**After:** `It's harder than it sounds.`

**Before:** `It wasn't only that. It was a philosophical choice about what I was trying to build.`

**After:** `It was that, but it was also something bigger.`

The second example refuses to name the thing precisely. "Something bigger" is vaguer than "a philosophical choice," but it's also truer to how it feels when you're in the middle of it.

---

## 9. Italics as Significance Signals

When an LLM wants you to know that a term matters, it italicizes it. *Procedure*. *Intent*. *The critical insight*. It's the typographic equivalent of clearing your throat before saying something important.

Remove them. If the sentence is written well enough, the terms carry their own weight. If it isn't, italics won't fix it.

---

## 10. Staccato Sentences That Should Be One

LLMs often split a single thought across three or four very short sentences for rhythmic effect. Read aloud, it sounds like someone pausing dramatically after every clause. In prose, it gets tiring quickly.

**Before:** `The coordinator wasn't uncertain. She had checked the rule. The rule was clear. She had done exactly what the protocol required.`

**After:** `The coordinator wasn't uncertain. She'd checked the rule, it was clear, she'd done exactly what the protocol required.`

**Before:** `I had already agreed to record with my next guest. He had said yes and we had a date on the calendar.`

**After:** `I had already agreed to record with my next guest and we had a date on the calendar.`

The second example also removes a redundancy: if you've already agreed, obviously he said yes.

---

## 11. Redundant Restatements

LLMs say something and then immediately say it again at slightly higher resolution, as though clarifying a point they'd already made clearly. Cut the first version, or merge them.

**Before:** `The feeling was surreal. It was, honestly, a feeling of being on top of the world.`

**After:** `Honestly, I felt like I was on top of the world.`

**Before:** `Through all of this, the quiet early period, the near-quit, the recognition, one thing anchored everything: the website.`

**After:** `Through all of it, one thing anchored everything: the website.`

The list in the original (quiet early period, near-quit, recognition) is decoration. It doesn't add information. It adds the appearance of thoroughness.

---

## 12. Corporate Prepositions and Formal Phrasing

Small vocabulary choices accumulate. "Post these episodes" instead of "after those episodes." "Prior to" instead of "before." "In the context of" instead of "when." Each one is a minor thing; together they give the prose a slightly institutional register that doesn't belong in personal writing.

**Before:** `Post these episodes, the downloads picked up.`

**After:** `After those two episodes, the downloads picked up.`

**Before:** `Before you ship the next version... apply one check. Take any conclusion... Ask: could it have arrived...`

**After:** `Before you ship the next version, try one thing. Take any conclusion and ask whether it could have arrived there the same way even if the answer was wrong.`

---

## 13. Nominalized Emotion

When something genuinely moved the writer, LLMs describe the emotion by naming it: "a sense of," "a feeling of," "a recognition that." It's describing an emotion from the outside rather than expressing it from the inside.

**Before:** `What I took from those two episodes was not about content or topics.`

**After:** `The lesson from those two episodes wasn't really about content or topics.`

**Before:** `It was a feeling of being on top of the world.`

**After:** `I felt like I was on top of the world.`

The original puts the feeling in a noun phrase. The revision just says the thing.

---

## 14. Performative Instruction Closers

LLMs love to end a piece with a directive. "Before you do X, try Y. Ask yourself Z. Take the following steps." It signals completeness, the sense that the essay has now translated into action. But it can feel like a checklist appended to a piece of writing that was doing fine without one.

**Before:** `Before you ship the next version... apply one check. Take any conclusion... Ask: could it have arrived at the same place even if the premises were wrong?`

**After:** `Before you ship the next version, try one thing: take any conclusion and ask whether it could have arrived there the same way even if the answer was wrong.`

The revision is still a directive. It's just a sentence, not a procedure.

---

## 15. Meta-Commentary Transition Phrases

LLMs narrate the structure of their own argument as they go. "It is worth noting that." "It is important to understand that." "Having established X, we can now turn to Y." "With that in mind." These phrases don't move the argument forward. They announce that the argument is about to move forward, which is different.

Cut them. Just say the next thing.

**Before:** `It is worth noting that the timing here matters.`

**After:** `The timing matters.`

**Before:** `It is important to understand that this was not a planned decision.`

**After:** `This wasn't a planned decision.`

**Before:** `With that in mind, let us consider how this applies to system prompts.`

**After:** `The same logic applies to system prompts.`

**Before:** `Having established the problem, we can now turn to solutions.`

**After:** *(just start the next paragraph)*

---

## 16. Importance-Signaling Adverbs

"Importantly," "Notably," "Interestingly," "Crucially," "Significantly." These are the writer telling the reader what to find interesting rather than trusting the content to do it. If the thing is important, the reader will notice. If it isn't, the adverb won't help.

Remove them. Every one.

**Before:** `Notably, the downloads picked up after that episode.`

**After:** `The downloads picked up after that episode.`

**Before:** `Crucially, the route table is computed state, not configured state.`

**After:** `The route table is computed state, not configured state.`

**Before:** `Interestingly, the most successful episode came right after I had nearly quit.`

**After:** `The most successful episode came right after I had nearly quit.`

---

## 17. Intensifier Openers

"At its core." "The reality is." "Fundamentally." "What this really means is." These phrases try to signal that what follows is the deep truth, stripped of surface noise. But they mostly just add words before the actual sentence.

**Before:** `At its core, this is a question about trust.`

**After:** `This is a question about trust.`

**Before:** `The reality is that most system prompts are written as lists of rules.`

**After:** `Most system prompts are written as lists of rules.`

**Before:** `Fundamentally, the problem is that we're encoding outcomes instead of structure.`

**After:** `The problem is that we're encoding outcomes instead of structure.`

---

## 18. "In Other Words" Restatements

LLMs use "in other words" to restate something they just said clearly. Occasionally this is useful, when the restatement is in genuinely simpler terms. Usually it just says the same thing twice and pads the word count.

**Before:** `The route was correct but the traffic was still blocked. In other words, routing wasn't the issue.`

**After:** `The route was correct but the traffic was still blocked. Routing wasn't the issue.`

**Before:** `The system prompt describes what to do, not why. In other words, it encodes procedure, not principle.`

**After:** `The system prompt describes what to do, not why. Procedure, not principle.`

If you cut "in other words" and the sentence still works, it should go.

---

## 19. Thesaurus Vocabulary

LLMs reach for the more sophisticated synonym even when the simpler word is right. "Facilitate" instead of "help." "Leverage" instead of "use." "Demonstrate" instead of "show." "Endeavour" instead of "try." "Optimal" instead of "best." Individually these are minor. Accumulated across a piece, they give the writing a formal, slightly airless quality.

**Before:** `This will facilitate a better understanding of the problem.`

**After:** `This will help you understand the problem.`

**Before:** `We need to leverage the existing infrastructure.`

**After:** `We can use what's already there.`

**Before:** `The results demonstrate a clear pattern.`

**After:** `The results show a clear pattern.`

**Before:** `This endeavour requires patience.`

**After:** `This takes patience.`

The rule is: if a shorter, older word does the same job, use it.

---

## 20. Explicit Lesson Extraction

LLMs name the takeaway at the end of every anecdote or argument. "What this tells us is." "The lesson here is." "What emerges from this is." It's writing that doesn't trust the reader to draw conclusions. Sometimes the naming is useful. Mostly it's just the LLM making sure nothing was missed.

**Before:** `What this tells us is that the timing mattered as much as the content.`

**After:** `The timing mattered as much as the content.`

**Before:** `The lesson here is that long shots are worth taking when your foundation is real.`

**After:** `Long shots are worth taking when your foundation is real.`

**Before:** `What emerges from this is a clear principle: start before you need it.`

**After:** `Start before you need it.`

State the conclusion. Don't announce that you're stating it.

---

## 21. Forward-Signaling Sentences

LLMs preview what's coming before it arrives. "What follows is." "The question then becomes." "This raises a further question." In a presentation these transitions make sense. In prose they slow things down. The reader is about to read what follows. They don't need to be told it's coming.

**Before:** `What follows is a breakdown of the three key decisions I made during this period.`

**After:** `Three decisions defined this period.`

**Before:** `The question then becomes: how do we encode this distinction in a system prompt?`

**After:** `How do you encode this distinction in a system prompt?`

**Before:** `This raises a further question: what happens when the model is confident and wrong?`

**After:** `What happens when the model is confident and wrong?`

---

## 22. The "Not Just X, But Y" Elevation

LLMs like to reframe a concrete problem as something deeper. "This is not just a technical problem, it is a philosophical one." "Not just about routing, but about how we reason about state." The construction isn't wrong, but it's used so reflexively that it starts to feel like a tell. Every problem gets elevated. Every surface issue reveals a deeper one.

When you find yourself writing "not just X, but Y," ask whether the elevation is earned. If the deeper thing is real, name it directly. Don't use the construction as a shortcut.

**Before:** `This is not just a technical problem, it is a philosophical one.`

**After:** `The technical problem was real. But underneath it was something harder to name.`

**Before:** `The challenge here is not just about routing, but about how we reason about state.`

**After:** `Routing was the surface problem. The deeper one was how we reason about state.`

The revision still makes the same point. It just doesn't announce that it's making it.

---

## The Underlying Pattern

Reading back through these, I notice they're all versions of the same thing. LLMs optimise for clarity and completeness. They resolve ambiguity, balance sentence structures, signal importance, and close arguments. Those are good instincts. But they produce writing that feels finished in a way that most good writing isn't.

The best human writing keeps a little unresolved. It scopes its claims carefully. It lets the reader feel the writer working something out, not presenting a completed analysis. It says "I think" and "I'm not sure" and "it's harder than it sounds" because those are honest.

The goal of humanizing isn't to make writing worse. It's to let the writer back in.

---

## If You Use Claude Code

These twenty-two patterns are built into a `/humanize` skill. Point it at any markdown file and it applies all of them in a single pass, then lists every change it made grouped by principle.

The skill is available at [repo-url] on GitHub.
