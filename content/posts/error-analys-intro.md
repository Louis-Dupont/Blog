+++
date = '2025-02-14T12:00:00+01:00'
draft = false
title = 'Error Analysis 🔧 Stop Guessing, Start Fixing AI Models'
+++

Error analysis is about digging deep into _why_ something isn’t working - to learn from it. It might sound obvious, but it's shockingly underused, especially where it matters most: AI development.

Let's explore what it is through an example

## Cats or Dogs ?

_I'm skipping many details that may hurt Data Scientists for the sake of simplicity._

Say you have 200 images to classify as either cats or dogs. You build an AI and get **78% accuracy** - not great. We need to do better. But how?

The typical response?

- _"Let's try another model"_
- _"Let's tweak the (hyper)parameters and hope for the best."_

Basically, this means blindly exploring different solutions to see what sticks. Then, we _hope_ to learn something and slowly converge on a better solution.

_But what if you could already learn what you want with this very first run?_

### Let's do error analysis!

You dig into your data and realize:

1. Some puppies were classified as cats.
2. Some images are completely dark - even you can't tell if it's a cat or a dog!
3. Finally, some were actually mislabeled!

After removing these irrelevant samples (_points 2 & 3_), your model actually achieves **97% accuracy**! The remaining 3% error comes from puppies being misclassified as cats.

The problem was not your model, but the data it was given.

Well, _almost._ There's still the issue of puppies being misclassified - this is a **failure mode**.

### What does this actually mean?

In this case, we have 3 clear action items:

- Correct the mislabeled samples.
- Find a way to make to model better on puppy images (there are many!).
- Ensure proper lighting for production cameras 🤷‍♂️
- ... and plenty more!

Then, next iteration, do the same, you may find out new problems!

Basically, **error analysis is what moves you past blindly tweaking solutions in hopes of improvement**. Instead, it shifts the focus to understanding the root causes of failure and addressing them directly.
