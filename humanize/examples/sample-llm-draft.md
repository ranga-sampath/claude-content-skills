# Why I Started Writing Custom Claude Skills — and What Happened Next

There is a moment every builder hits — the moment when the off-the-shelf tool stops being enough.

It was not that Claude was performing poorly. It was that I was asking it to do the same technical analysis repeatedly, and each time I had to re-explain the context. Importantly, this was not a failure of the model. It was a failure of the workflow.

## What Changed

Prior to writing my first custom skill, my workflow looked like this: open Claude Code, paste in the relevant context, type out the analysis request, wait for a response. Procedure produces consistency. Workflow produces repetition.

The skill changed that. Every time I ran `/my-skill`, the same context, the same analysis framework, the same output format — all applied automatically.

Notably, the improvement was not just in speed. It was in quality. Every senior engineer who has reviewed an AI output that looked great one day and mediocre the next understands the problem. The skill eliminated that variance.

## The Deeper Point

At its core, this is not a story about tooling. It is a story about the difference between using a tool and shaping it to fit the work.

It is worth noting that writing your first skill feels like over-engineering. It is important to understand that this feeling passes the third time you run `/your-skill` instead of typing out the same 200-word context from memory.

What this tells us is that the return on a well-written skill is not linear. The first run breaks even. The tenth run pays it off. Every run after that is free.

The reality is that most builders delay writing their first custom skill too long. They leverage the model's raw capability when a small amount of structure would give them something far more reliable.
