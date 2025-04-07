+++
date = '2025-04-01T16:32:04+01:00'
draft = false
title = 'How to Build Evals That Drive Impact'
+++

When you set up evaluation, you’re not just adding a score.

You’re building a **system that decides what "good" looks like**.

Most teams don’t treat it that seriously. They build evals by convenience. Automate too early. Use generic metrics. Plug in LLM-as-a-Judge with a vague prompt and hope it works.

It looks scientific, but in practice it’s just noise. Eventually they end up with an AI that does great on their internal benchmark but that none of their users really sticks to.

Why does this happen ? They skip the part where they actually learn what matters.

So before going further, quick sanity check:

- Did you identify and name the recurring ways your system fails?
- Have you already scored your AI manually?

If not, you’re not ready to build evals yet. Start here instead → [Learn to Systematically Improve your AI](../../articles/learn-to-systematically-improve-your-ai)

For everyone else, let’s fix the way you scale how **_you_** evaluate.

## What If You Could Scale _Yourself_?

Let’s say you already did the work. You looked at logs. You tagged outputs. You saw patterns. You built a clear view of where your model fails, and what a good answer should look like.

Great. Now comes the bottleneck: you can’t do that at scale.

It doesn’t matter if your intuition is right if it’s not repeatable.

So here’s the real goal: **turn your own judgment into a repeatable process**. You’re not looking for an hypothetical best metric. You’re teaching the system to approximate what _you_ already know matters.

And the best way to do that? Train an evaluator to mirror your decisions. Not someone else's framework. Not some generic leaderboard metric. Just _you_, scaled.

Let’s walk through how to do that with an LLM.

## Structure the Evaluation

Start with your evaluation vocabulary. If you’re using continuous scores (like 1–100), you’re asking for trouble. LLMs don’t do well with regression. And even humans struggle to be consistent there.

You can work with a set of categories, but the best format remains boolean labels. Pass/Fail, for each failure mode.

Not “score from 1 to 5”, but "was the Booking successfull?", "is it too verbose?", "did it miss the user's intent?" Each with a yes/no answer.

This forces clarity. And it’s far easier to match with a structured output later.

If you’ve already labeled your data this way, you’re ahead.

If not, I encourage you to do so. You can check my articles that talks about it → [Learn to Systematically Improve your AI](../../articles/learn-to-systematically-improve-your-ai)

## Onboard your Judge

Now that you have structured labels, it’s time to build the evaluator.

Use an LLM, but treat it like onboarding a new teammate. You wouldn’t give them a checklist and hope for the best. You’d show examples, walk through edge cases, and explain what good looks like.

That’s your prompt.

> Tip: Structured outputs help here. Force the output to match the format of your labels.

## Check Alignment

This is where most teams get lazy. You ask the Judge to score the same examples you already scored. Then you check: how often do you agree?

Look at _where_ you disagree. Are the disagreements meaningful? Are they edge cases? Or signs that your judge just doesn’t get it?

You don’t need perfect overlap. But you do need _predictable alignment_. If you and the Judge are in sync most of the time, that’s enough to trust it for early filtering.

> As you improve your Judge, you’ll start to see your own criteria more clearly. You’ll notice which patterns are easy to encode, and which are fuzzy. You might even revise what you thought "good" meant.
>
> It means you’re not only building an eval, you’re also refining understanding.

## Test Generalisation

So it agrees with you on the data you gave it. Great. But how well will it do on new samples?

How do you know you didn’t just select the Judge that just does great on the exam materials but didn’t learn your reasoning?

You need to check.

Take more samples that were not used to evaluate the Judge - if needed annotate more - and check how well it does.

> Overfitting isn’t just a model problem. It happens when you unconsciously tune your prompts too tightly around a specific dataset.

Even if your Judge agrees with you on your sample, it might still fail on new samples.

To check that, take a fresh set of examples - ideally fresh from production - and score them manually. Then compare with the Judge’s output.

This is your holdout set. It tells you if you’ve overfit the evaluator to your sample. If it doesn’t generalise, revisit your prompt, your labels, or your definition of “good.” You also may want to add more samples to make it more robust to overfitting.

## What You’re Actually Doing

At this point, it’s worth being clear about what’s happening.

You’re not just “setting up evals.”

You’re training a classifier.

The method is prompting, not fine-tuning. But the logic is the same: supervised learning.

That means the usual rules apply.

- Garbage in, garbage out
- Overfitting happens fast
- Bad labels lead to bad models

Once you see it like this, it becomes obvious why most evaluation setups collapse. They’re doing machine learning without treating it as such.

> If you're hitting limitations, you can go beyond LLM-as-a-Judge. Fine-tune a small classifier. Train a discriminative model. But for most teams, that’s overkill.

## From Clarity to Speed

When your evaluator works - when the proxy you’ve built reflects your actual judgment - you unlock speed.

You can filter outputs at scale. Detect regressions automatically. Run batch experiments and know what matters. Align your team on a quantitative definition of quality. Stop relying on gut feel.

You don’t need to track every edge case. But you do need to trust that your eval reflects something real.

That’s the difference between guessing and engineering.

That’s how you go from “vibe check” to deliberate iteration, so you can scale with speed _and confidence_.

[Read my Blog →](../../articles/)  
[Learn how I can help →](../../work-with-me)
