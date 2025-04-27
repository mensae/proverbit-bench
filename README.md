# ProberbIT Benchmark

Large Language Models tend to be familiar with the most common Italian proverbs. Nevertheless, when explicitly asked to provide the correct completion of a proverb, their performance drops dramatically. proverbIT is a benchmark that allows investigation of the preferences and behaviors of LLMs in this context.


# Dataset & Task Description

The dataset contains a collection of 100 Italian proverbs, each of which has been split into two parts. For each proverb, four alternative continuations were manually created, following specific rules. In particular:

- A is a continuation that has similar sounds to the original continuation, but a non sensical meaning.
- B is a non-rhyming synonym of the original continuation.
- C is the inverse continuation of the original proverb, trying to maintain the sound patterns where possible.
- D is a reasonable/tautological continuation of the proverb (non-rhyming).

Considering for instance the proveb `A buon intenditore, poche parole` (which literally translates as "to a wise man, a few words") the prompt provided to the LLMs is the following (originally in Italian, here translated for readability between squared brackets):

```
Complete the proverb exactly by choosing from the following options (which have no typing errors) indicating only the letter.
If none is correct, answer 'None'.

A buon intenditor,... [to a wise man...]

A) ...foche canore [...singing seals]
B) ...zero chiacchiere [...zero chatter]
C) ...molte parole [...many words]
D) ...è chiaro tutto [...everything is clear]

Do not add comments, the possible answers are only A, B, C, D, None.
```

# Evaluation

Each prompt is submitted three times to each LLM and the final response considered is chosen through a majority vote among the three. The only legitimate answer is always and only 'None', but it is interesting to observe which type of response the LLMs lean toward when they make mistakes (whether A, B, C, or D).


This repository contains 10 samples of the dataset, you can check out the leaderboard and evaluation results on the [official webpage](https://enkk.me/proverbit). 
