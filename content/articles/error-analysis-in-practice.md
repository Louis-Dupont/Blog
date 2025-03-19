+++
date = '2025-03-18T15:42:04+01:00'
draft = false
title = 'Unblock Your AI (For Good)'
+++

Many teams I’ve worked with start out making rapid progress with their AI - usually a RAG system. At first, iteration is fast. Each tweak makes a visible difference. But then, they hit a plateau.

**Changes don’t seem to make a clear impact anymore**. Some changes even backfire. The AI isn't broken, but it’s no longer clear what to fix—or even how to tell if it’s improving at all.

## When Metrics Stop Making Sense

That’s when most teams turn to metrics. And **that’s where things usually go wrong.**

They set up a dashboard, plug in well-known evaluation metrics like faithfulness, informativeness, or completeness, and start tracking numbers.

The model is hitting good scores. But… **they're still lacking the clarity they were looking for.**

> _Our previous model scored 4.2 in informativeness, 4.6 in faithfulness, and 4.7 in completeness. The new model scores 4.9 in informativeness, 4.5 in faithfulness, and 4.6 in completeness. Should we go for it?_

And the reason is simple: these metrics aren’t actionable. They aren’t tied to real-world success.

A model could hit **100% faithfulness and still be useless.** Why? Because generic metrics don’t account for whether the AI is actually solving the problems your users care about.

Instead of focusing on some abstract measure of "quality," the real key to improvement is much simpler: understanding how and why your AI is failing.

This is where **manual error analysis** comes in.

## Stop Guessing — Start Working!

This isn’t glamorous. It’s not high-tech. **And that’s exactly why it works.**

You need to sit down with your logs, one by one, and look at what’s actually going wrong. It forces you to move beyond vague intuition and translate gut feelings into concrete, fixable problems.

It may feel slow at first. But **if you do it right, patterns will emerge.** And when they do, you’ll see your system’s failures more clearly than any generic metric ever could.

Here’s how it typically goes:

### First, you take a real sample of your logs.

Carefully go through each output and try to identify **recurring mistakes.** Once you do, list them. **These are your failure modes.**

- _"Misunderstands the query"_
- _"Refuses to answer the question"_
- _"Fails to retrieve the right source"_

Whatever they are, give them names. **Tag at least 50 queries (ideally hundreds).**

Now, you don’t just have a list of failures—you have a clear map of how often each one occurs.

**But you’re not done yet.**

Next, analyze your **user queries.** What are they actually asking? What **topics** keep coming back?

- _"Technical Troubleshooting"_
- _"Product Questions"_
- _"Pricing Questions"_

The real power comes when you combine these tags into a clear input topic vs. failure mode matrix.

| **Input Topic vs Failure Mode** | **Query Misunderstanding** | **Answer Refusal** | **Retrieval Failure** | **% of Queries** |
| ------------------------------- | -------------------------- | ------------------ | --------------------- | ---------------- |
| **Troubleshooting**             | 40%                        | 10%                | 5%                    | 85%              |
| **Product Questions**           | 10%                        | 10%                | 5%                    | 16%              |
| **Pricing Questions**           | 2%                         | 10%                | 90%                   | 2%               |
| **% of Error**                  | 34%                        | 10%                | 7%                    |                  |

You can now start to **prioritize and decide what to do next.**

Should you focus on fixing `Troubleshooting` first? Minimize `Query Misunderstanding` across all input topics? Drop support for `Pricing Questions`, since they’re rare and can be handled without a chatbot?

Well, that's a product decision, but **you now have all the cards in hand to take it.**

## Stay Far from Evals

At this stage, it’s tempting to start automating error tracking with Evals.

**And that’s a mistake.**

Evals work only when failure modes are well-defined and repeat across iterations. Jump in too soon, and you’ll likely end up tracking issues that don’t even matter.

There are two major ways premature automation backfires:

- **You measure the wrong thing.** If you automate before deeply understanding your failure modes, you’ll end up with weak metrics that mislead you.
- **You measure something that isn’t worth tracking long-term.** Some problems disappear after a few iterations. If you automate too early, you waste time tracking noise.

## Just Do It!

It’s work. It’s tedious. And it might feel slow at first.

But **this is the difference between engineering and guessing.**

When you do error analysis right:\
**→** You stop chasing abstract improvements and focus on real issues that impact users.\
**→** You prioritize fixes effectively, instead of throwing darts in the dark.\
**→** You know exactly when and where to automate, rather than wasting effort tracking things that don’t matter.\

AI teams rarely fail because they lack solutions.

They fail because they rush to conclusions. Automate the wrong metrics. Optimize in the wrong direction.

**Error analysis keeps you from making those mistakes.** It teaches you what truly matters.

It’s a continuous process—one that, **when done right, becomes the foundation for scalable Evals.**

[**Read my Blog →**](./articles/)  
[**Learn how I can help →**](./work-with-me)
