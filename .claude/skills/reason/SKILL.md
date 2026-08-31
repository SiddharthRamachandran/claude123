---
name: reason
description: Explain work that is already finished, in very simple English, as a short numbered list with one sentence per point. Use this whenever the user types /reason, and also whenever they ask for a plain explanation of something you did — "explain simply", "in simple words", "point by point", "what did you just do", "why did you pick that", "i don't get what you changed", "explain like I'm five". Reach for it even when the user never says the word "reason", as long as they are asking you to explain finished work rather than asking you to do new work.
---

# Reason

## What this is for

Someone is asking about work that is already done, and they want to *understand* it, not read a wall of text about it. They may not write code. English may not be their first language. They may be reading on a phone.

So the job is not to summarize. The job is to make a person genuinely understand what happened, using the smallest words that are still true.

## The shape of the answer

A numbered list. That's the whole answer — no opening sentence, no closing summary, no headings, no sub-bullets.

- **One point = one line = one sentence.** If a point needs two sentences, it is really two points, or it is one point trying to say too much.
- **Point 1 answers the question directly.** If they asked "why did you use 30 pages?", point 1 says why. Don't make them read to point 6 to find the answer.
- **Aim for about 8 points, and never more than 10.** Four or five is right for a small question.
- **Ten is a wall, not a target.** If you have twelve things to say, that means two of them are small enough to merge and one is not worth saying — do that work yourself instead of handing the reader a longer list. A person remembers eight lines; they skim twelve and keep three.
- **Never pad.** If the honest answer is five points, give five. Adding filler to reach eight makes the list worse, not more complete.
- **Put the biggest thing first and the smallest last.** The reader should be able to stop halfway and still have the important half.
- **Keep each line short** — around fifteen words. Long lines wrap in a terminal and stop looking like a list.

The user asked for this shape on purpose: they want to scan the answer in ten seconds and be able to point at the one line they don't understand. An intro paragraph defeats that.

## How to write each line

Write like you are explaining to a smart person who has never seen this kind of work before. They are not slow — they just don't know your words.

- Use everyday words: *made*, *used*, *fixed*, *checked* — not *implemented*, *leveraged*, *utilized*, *validated*.
- Say what a thing **does**, not what it **is**. "It draws the pictures when you open the page" beats "it's a rendering engine."
- Compare to real things when it helps. "Like flipping the corner of a notebook" lands; "frame-sequenced playback" does not.
- Say "I" for what you did. Own it — "I removed the old file", not "the old file was removed".
- Describe it from the outside. Say what the person can see, use, or decide — not how the code is arranged inside. "Every line is drawn in the darkest grey" is worth a point; "every line goes through one shared drawing helper" is a fact about the code that means nothing to them. Go inside only if the question was about the code.
- Give the reason, not just the fact. "I used 30 pages because fewer looked jumpy" teaches something; "I used 30 pages" doesn't.
- Include the honest points too — what broke, what you skipped, what is still missing. A list of only good news is not an explanation, it's an advertisement.

## Hard words

When something has a real technical name that is worth knowing, say it in plain words first, then put the real name in brackets at the end of the line.

> 3. Things far away move slower than things close up (this is called parallax).

This way the line reads fine even if they skip the brackets, and they slowly pick up the real words. Write "(this is called parallax)" rather than bare "(parallax)" — a lone word in brackets looks like a label, and the reader can't tell it's the name of the thing you just described.

Two limits keep this from becoming noise: at most one bracket per line, and only for names that are actually worth carrying away. Don't gloss a word you could have simply avoided.

## Get the facts right first

This skill answers "what did *you* do" — so being wrong is worse than being complicated. Before writing, look at the real thing: read the file, the diff (`git show`, `git log`), the test output, the earlier messages. Don't reconstruct it from memory if you can check it in five seconds.

If you don't know, say that in a point and stop guessing:

> 5. I don't know why that test fails — I have not looked at it yet.

## Examples

**Question:** "/reason what did you do to make the animation?"

```
1. I made one file, flipbook.html, that holds the whole thing.
2. The book has 30 pages, and each page is one drawing.
3. The computer draws every line, so no two pages look the same.
4. That small difference is what makes the drawings feel alive (this is called boiling line).
5. The pages swap about 12 times a second, like a real flipbook.
6. The cat moves its four legs in a real running pattern.
7. The mouse stays in front, and the gap gets bigger and smaller.
8. A small car crosses the far road once, from page 1 to page 30.
```

**Question:** "/reason why is the cat so big compared to the mouse?"

```
1. I drew the cat about four times taller than the mouse on purpose.
2. A real cat is much bigger than a real mouse, so it looks right.
3. It also makes the chase feel unfair, which is the fun part.
4. A small cat next to a big mouse would look like two mice running.
5. The cat is 48 units tall and the mouse is 22, inside a page 480 tall.
6. I can make either one bigger if you want them closer in size.
```

Notice what both lists do: the first line answers the question, every line is one sentence, and the last line often gives the person something they can decide or ask about next.

## What not to do

- Don't write a paragraph and then a list. The list is the answer.
- Don't paste code, unless they asked to see it. A file name is usually enough.
- Don't say "as mentioned above" — each line stands on its own.
- Don't apologize or hedge across three lines. Say the problem once, plainly.
