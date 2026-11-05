---
name: readable-prose
description: Write or revise English prose for first-pass readability. Use for explanations, reports, summaries, emails, documentation, and drafts that sound like AI.
---

# Readable prose

Source: Clark, Martin & Mahowald, [Why is AI-generated language so hard to understand?](https://arxiv.org/abs/2610.29162) (2026).

## The core idea

The paper finds that post-trained LLMs choose the *shorter* of two ways to say the same thing far more often than humans do, even when the shorter form is harder to read. The authors propose that training pressure for shorter answers can encourage this pattern. A fine-tuning experiment with a length penalty provides evidence for that hypothesis.

So the rule is: **when a shorter form and a clearer form compete, pick the clearer one.** A few extra words are cheap. A sentence the reader must parse twice is not.

Keep the content concise. Cut preamble, recap, and padding. Use a few extra words when they make a sentence easier to understand.

## The seven features to avoid

The paper measured these. Each has a fix that costs a few words.

### 1. Inanimate subjects doing animate things

A file, a bug, a function or a constraint "bites", "swallows", "wants", "eats", "fights", "complains", "hides". The reader expects a living subject for these verbs, hits a mismatch, and must reanalyze. All nine models tested overused this.

- Avoid: "The cache swallows the error and returns nothing."
- Write: "The cache catches the error, ignores it, and returns nothing."
- Avoid: "This is where the off-by-one bites."
- Write: "This is where the off-by-one error causes a wrong result."

Test: would the verb fit a person or animal better than the thing it describes? Then name the actual event.

### 2. Rare word combinations (low-frequency n-grams)

Pairings a reader has never seen before ("reader-patience budget", "load-bearing assumption", "token-cheap path") force them to build the meaning from scratch. All nine models overused these.

- Prefer the common phrase for the idea, even if it is longer.
- If a new coined term is necessary, define it once in plain words and then reuse it exactly.
- Metaphors are coined phrases too. Use one only if it is common English and adds something the literal phrase does not.

### 3. Stacked nouns (three or more nouns in a row)

"user session token refresh failure" makes the reader guess the bracketing. Is it a failure of the token refresh, or a refresh of the failure token?

- Avoid: "the build cache invalidation bug"
- Write: "the bug that stops the build cache from being invalidated"
- Two nouns ("build cache") are fine. At three, unpack with "of", "for", or a verb.

### 4. Ad-hoc denominal verbs (nouns used as verbs)

"Footnote it", "calendar it", "ticket this", "PR it", "README that". Conventional ones ("email", "bottle", "test") are fine. New ones make the reader reparse the word class.

- Avoid: "Let's ticket this and changelog it."
- Write: "Let's open a ticket for this and add it to the changelog."

Test: would a dictionary list this word as a verb? If not, use a verb phrase.

### 5. Reduced object relative clauses (dropped "that")

"The fix the reviewer suggested broke the tests." The reader has no signal that a relative clause started. Models dropped the optional "that"/"which" much more than humans.

- Write: "The fix that the reviewer suggested broke the tests."
- Better still, when the sentence is complex, make it a subject relative or split it: "The reviewer suggested a fix. It broke the tests."
- In general, keep optional function words ("that" after "said", "so that", "sure that") when the next part is long or unexpected.

### 6. Object relative clauses in general

Even with "that", object relatives ("the module that the parser imports") are harder than subject relatives ("the module that imports the parser") or plain clauses. Use them only when they are short. Prefer active main clauses: "The parser imports this module."

### 7. Long dependencies

Keep each subject close to its verb and each verb close to its object. Long gaps strain working memory.

- Avoid: "The function, which after the refactor last week now also handles retries and logs each attempt to the audit table, returns null."
- Write: "The function returns null. Since last week's refactor, it also handles retries and logs each attempt to the audit table."
- Put long modifiers after the main clause, not between subject and verb.
- Prefer two sentences over one sentence with an interruption.

## Where the risk is highest

- **Long, many-turn conversations and coding sessions.** The paper found the effects were strongest in chat and coding, weaker in single-turn essays. Late in a long session, check harder.
- **Code explanations.** Personifying code ("the loop wants", "the API hates") is the most common form of feature 1.
- **Summaries under a length limit.** A tight limit pushes toward features 2, 3 and 4. Cut content, not grammar.

## Before sending: the check

Scan the draft once for each item. Fix every hit.

1. Any verb that fits a person better than its non-living subject? → name the real event.
2. Any phrase you invented, or would not find in ordinary text? → common phrase, or define it once.
3. Three or more nouns in a row? → unpack.
4. Any noun used as a verb that a dictionary would not list? → verb phrase.
5. Any "the X [someone] did" without "that"? → add "that" or split the sentence.
6. Any subject separated from its verb by a clause? → move the clause or split.
7. Read the sentence once, fast. Did you have to go back? → rewrite it.

## Scope

The paper studied English. For other languages, use the wording that reads most naturally in that language.
