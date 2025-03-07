+++
date = '2024-12-20T16:22:38+01:00'
draft = false
title = '🤷‍♂️ ModernBERT Is Here - and It’s Not Just Another LLM Update'
+++

BERT is back - and this time, it’s **faster, smarter, and built for the tasks that matter.**

If you’re working on **retrieval**, **classification**, or **code search**, encoder models like BERT have likely been your go-to. Generative LLMs may grab headlines, but **when it comes to focused, production-ready AI tasks, BERT still shines**.

Earlier this year, I ran an experiment comparing models on a real-world task—analyzing product reviews. The results were eye-opening:

- GPT-4o hit 91% accuracy with a cost of $1.40 per 1,000 reviews.
- After fine-tuning, Phi-3 mini matched GPT’s accuracy but ran locally, with 2.7 seconds per review.
- But the real surprise? **6-year-old BERT** hit **97% accuracy**, with processing speeds of just 0.03 seconds per review.

This showed me that while LLMs excel at text generation and versatility, **BERT dominates when you need precision and speed.**

### Why ModernBERT Is a Big Deal

ModernBERT takes everything that made the original BERT great and levels it up:

- **3x faster inference speeds.**
- **8k token context length** (vs. 512)—perfect for full-document retrieval.
- **Trained on code**, unlocking large-scale code search and smarter IDE tools.

Generative models won’t replace what encoder models like BERT do best. If you’re building systems that need structured outputs, retrieval pipelines, or highly targeted classification, this release is worth your attention.

And for the full details on ModernBERT: [https://huggingface.co/blog/modernbert](https://huggingface.co/blog/modernbert)
