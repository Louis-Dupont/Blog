+++
date = '2025-03-18T15:42:04+01:00'
draft = false
title = 'Unblock Your AI Project (For Good)'
+++

Many teams I’ve worked with start off with rapid progress in developping their AI - usually a RAG system. At first, iteration is fast. Each tweak brings noticeable improvements. But then, they hit a plateau.

What used to feel obvious now feels uncertain. Changes don’t seem to make a clear impact anymore. Some even backfire. The system isn't broken, but it’s no longer clear what to fix—or even how to tell if it’s improving at all.

## When Metrics Stop Making Sense

That’s when most teams turn to metrics. And that’s where things usually go wrong.

They set up a dashboard, plug in well-known evaluation metrics—faithfulness, informativeness, recall—and start tracking numbers.

The model is hitting good scores. And yet… they're still lacking the clarity they were looking for.

> _Our previous model scored 4.3 in informativeness, 4.6 in faithfulness, and 4.7 in completeness. The new model scores 4.6 in informativeness, 4.5 in faithfulness, and 4.6 in completeness. Should we go for it?_

And the reason is simple: these metrics aren’t actionable. They aren’t tied to real-world success.

A model could hit 100% faithfulness and still be useless. Why? Because generic metrics don’t account for whether the AI is actually solving the problems your users care about.

Instead of focusing on some abstract measure of "quality," the real key to improvement is much simpler: understanding how and why your AI is failing.

This is where manual error analysis comes in.

## Stop Guessing — Start Working!

This isn’t glamorous. It’s not high-tech. And that’s exactly why it works.

You need to sit down with your logs, one by one, and look at what’s actually going wrong. It forces you to move beyond vague intuition and translate gut feelings into concrete, fixable problems.

It may feel slow at first. But if you do it right, patterns will emerge. And when they do, you’ll see your system’s failures more clearly than any generic metric ever could.

Here’s how it typically goes:

**First, you take a real sample of your logs**. Carefully go through each output carefully and try to identify recurring mistakes. Once you do, list them. These are the Failure Modes.

- "Misunderstands the query"
- "Refuses to answer the question"
- "Fails to retrieve the right source"

Whatever they are, give them names. Tag at least 50 queries (ideally hundreds).

Now, you don’t just have a list of failures—you have a map of how often each problem happens.

**But you’re not done yet.**

Now, do the same for your user queries. What are they actually asking? What **topics** keep coming back?

- "Technical Troubleshooting"
- "Product Questions"
- "Pricing Questions"

The beauty comes when you combine these tags into a clear matrix - topic vs. failure modes.

| Input Topic vs Failure Mode | Query missunderstanding | Answer Refusal | Retrievial Failure | % of Queries |
| --------------------------- | ----------------------- | -------------- | ------------------ | ------------ |
| Troubleshooting             | 40%                     | 10%            | 5%                 | 85%          |
| Product Questions           | 10%                     | 10%            | 5%                 | 16%          |
| Pricing Questions           | 2%                      | 10%            | 90%                | 2%           |
| % of Error                  | 34%                     | 10%            | 7%                 | 100%         |

You can now start to prioritize and decide what to do next.

Should you optimize for a specific input topic ? Or failure mode? Support only 2 out of 3 topics ?

Well, that's a product decision, but you now have all the cards in hand to take it and decide on what to prioritize.

## Stay Far from Eval

At this stage, it’s tempting to start automating error tracking with Evals.

And that’s a mistake.

Evals work only when failure modes are **well-defined** and **repeat across iterations**. If you jump in too soon, you will probably end up tracking issues that aren’t worth measuring.

There are two major ways premature automation backfires:

- **You measure the wrong thing**. If you automate before deeply understanding your failure modes, and end up with a weak metrics that mislead you.
- **You measure something that isn’t worth tracking long-term**. Some problems disappear after a few iterations. If you automate too early, you waste time tracking noise.

This is why **manual analysis comes first**. Only automate when a failure mode proves to be recurring across multiple iterations. Otherwise, you’re just losing time adding unneeded complexity.

## Exclusive Bonus

There’s another key benefit to doing error analysis right: **you discover when a single approach isn’t enough.**

Maybe a retrieval tweak boosts retrievial quality for pricing queries—but makes it worse for product questions.

Maybe a prompt change helps customer service requests—but affects technical answers.

**If fixing one input topic thing hurts another**, that’s a clear sign that you shouldn’t be trying to force a single solution. **You need routing**.

And here’s the good news: you’ve already done the hard work.

Since you’ve tagged and categorized failures, you already know which types of queries struggle with which failure modes. Now, you can design a simple routing system:

- When a query is about pricing, send it through a pricing-optimized prompt.
- When it’s a troubleshooting request, adjust retrieval settings to favor technical accuracy.

Each query type gets a specialized pathway, rather than forcing one-size-fits-all responses.

This approach massively boosts accuracy—because instead of making trade-offs, you’re optimizing each case individually.

## Just Do It!

This is work. It’s tedious. And it might feel slow at first.

But this is the difference between engineering and guessing.

When you do error analysis right:

✅ You stop chasing abstract improvements and focus on real issues that impact users.

✅ You prioritize fixes effectively, instead of throwing darts in the dark.

✅ You know exactly when and where to automate, rather than wasting effort tracking things that don’t matter.

Most AI teams don’t fail because they lack good models.

They fail because they lack a clear, systematic way to improve them.

Error analysis is the cornerstone of that system.
