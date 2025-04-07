+++
title = 'Where Are You Stuck? → 6 Questions to Diagnose your AI'
date = '2025-03-28T16:00:00+01:00'
draft = false
+++

You’ve built a chatbot. Maybe even launched it. You’ve made changes—prompt tweaks, retrieval tricks, some reranking logic. It’s probably better than it was. But is it _really_ getting better? Can you tell? Most teams can’t. Not because they’re bad. Because they don’t have the right visibility.

That’s what this post is for.

If you're stuck, walk through these six questions. They’ll show you what’s missing.

---

### 1. Do you have logs?

Can you open up a list of recent conversations and look at what users said, what the system answered, and how the flow went?

- If yes → Great.
- If not → You’re flying blind. Nothing else in this post matters until you can look at real usage. Setup Monitoring, or, worst case, generate synthetic data to get started.

### 2. Have you read through them?

Can you show 5 examples where the system obviously helped, and 5 where it obviously failed?

- If yes → Good. You’re starting to build intuition.
- If not → You’re still guessing. Sit down. Read through 50 logs. It won’t take long. You’ll start seeing what’s _actually_ going wrong.

Learn how to do this step → [Learn to Systematically Improve your AI](../../articles/learn-to-systematically-improve-your-ai)

### 3. Have you named your failure modes?

You’ve seen some common problems. Did you write them down?

Things like:

- Misunderstands the query
- Retrieves wrong content
- Refuses to answer
- Too verbose
- ...

Can you confidently name them ?

- If yes → You now have something to work with.
- If kind of → Write them down. Make them real.
- If not → This is where your iteration should start. You can’t fix what you haven’t defined.

More on how to approach this → [Learn to Systematically Improve your AI](../../articles/learn-to-systematically-improve-your-ai)

### 4. Did you measure those failure modes?

Did you already measured the frequency of each failure mode on at least 50-100 samples?

- If yes → Great. Now you can track improvements.
- If not → Just do it manually. Automating too early is a trap. Manual is faster and will teach you more in the beginning.

### 5. Are your iterations targeting one of them?

When you ship a new version, are you doing it with specific failure mode(s) in mind?

- If yes → You’re finally iterating with purpose.
- If not → You’re just trying stuff. Stop. Pick the failure mode(s) that matters most, and work on only that for the next change.

If you don't know how to prioritize which failure mode → [Learn to Systematically Improve your AI](../../articles/learn-to-systematically-improve-your-ai)

### 6. Can you do this at scale?

Let’s say you’ve defined your failure modes, and you can measure them manually.  
Can you now track them consistently—across time, across changes, across eval sets?

- If yes → You’re in the rare group. This is what real eval looks like.
- If not yet → Learn [how to setup Evals that actually drive impact](../../articles/how-to-build-evals-that-drive-impact)

---

That’s it. Six questions.

Wherever you said “no,” that’s where you’re stuck.

You don’t need to fix everything at once. Just take the next step.

[Read my Blog →](../../articles/)  
[Learn how I can help →](../../work-with-me)
