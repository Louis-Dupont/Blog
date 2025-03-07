+++
date = '2025-01-02T10:00:00+01:00'
draft = false
title = "Evaluate your LLM! Ok, but what's next? 🤔"
+++

**Everyone say you need to Evaluate your LLM. You just did it. Now what? 🤷‍♂️**

You got a score. Great. Now, here’s the trap:

You either:

- **Trust it.** (_"Nice, let's ship!"_)
- **Chase a better one.** (_"Tweak some stuff and re-run!"_)

Both are **horrible ideas.**

## **Step 1: Stop staring at numbers.**

Numbers feel scientific, but **they lie all the time.**

Before doing anything, look at actual examples. **What’s failing?**

- Bad output? **Fix the model.**
- Good output but bad score? **Fix the eval.**
- Both wrong? **You’ve got bigger problems.**

## **Step 2: Solve the right problem.**

If your **model sucks**, tweak:

- Prompts
- Data retrieval
- Edge cases

If your **eval sucks**, rethink:

- Your scoring function
- What “good” even means

## **Step 3: Iterate like a maniac.**

Change something → Run eval → Learn → Repeat.

Basically, do [Error Analysis](error-analys-intro.md) on your Evals (instead of on your LLM)!

**Chasing numbers isn’t progress.** Chasing the right insights is.
