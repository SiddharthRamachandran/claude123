# What makes a cartoon funny, and what makes you unable to look away

Notes gathered for the flipbook in this repo. Two separate questions get mixed up a
lot, so they are kept apart here:

- **Funny** is about a single moment — a gag lands or it doesn't.
- **The hook** is about a character — you want to watch them before they do anything.

They use different machinery. A perfectly timed gag performed by a character nobody
cares about still dies.

---

## Part 1 — Why anything is funny

### The one theory with experiments behind it

Most writing on cartoon humour lists three old theories: **incongruity** (funny =
the gap between what you expect and what happens), **superiority** (funny = someone
else is worse off than you), and **relief** (funny = tension released). These show
up in every blog on the subject, usually with no evidence attached.

The version that has actually been tested is **benign violation theory** —
A. Peter McGraw and Caleb Warren, *Benign Violations: Making Immoral Behavior Funny*,
Psychological Science, 2010. Their claim is precise: something is funny when, and only
when, three things are true at once.

1. It is a **violation** — something is wrong, threatening, or not how the world ought to be.
2. It is **benign** — it is also simultaneously fine, safe, harmless.
3. **Both readings happen at the same time.** Not one then the other.

This explains the failure modes better than incongruity does. Pure violation is
horror, not comedy: a cat catching a mouse and eating it is not funny. Pure benign
is boring: a cat and a mouse sitting still is not funny. The comedy is in holding both.

What makes a violation benign, per the paper: there's an alternative reading where
it's acceptable, you're not strongly committed to the norm being broken, or you're
psychologically distant from it. **Cartoons get all three for free** — it's a drawing,
so nothing hurts, and you know it. That's why a cartoon can flatten a character with
an anvil and stay funny, while live action can't.

**The practical form:** hurt the character in a way that visibly costs them nothing.
The violation is the injury; the benign is that they get up.

### Timing is the mechanism, not a garnish

Every practitioner source says the same thing: timing decides whether a gag lands.
But specifically, the funny part is the **pause**, not the action.

The structure is *anticipation → action → hold*. The anticipation is a beat where the
character telegraphs what's coming, so the audience predicts it. The hold afterwards
is the beat where the character registers what happened — and that hold is where the
laugh actually goes. If you cut away immediately, the audience has nowhere to put it.

Classic Warner Bros. and Tom and Jerry gags run on this. The reason a character
runs off a cliff, stops, looks down, looks at camera, *and only then* falls, is that
the fall alone isn't funny — the pause before it is.

### The rest of the toolkit

- **Exaggeration.** Cartoons can break physics, and that's the point — the impossible
  reaction is a violation that is obviously benign.
- **Repetition, then a break.** The same gag three times sets a rule; the fourth time
  it goes wrong. The laugh is on the break, but it can't exist without the setup.
- **A pair with opposite temperaments.** Straight man and clown. The comedy is in the
  contrast, which is why chases are almost always big/dumb versus small/clever.
- **Sight gags in the background** that reward a second look.

---

## Part 2 — The hook: why you watch before anything happens

This is **appeal**, the twelfth of Disney's principles, and the hardest to fake.

### Silhouette is the test

Fill your character in solid black. If you can still tell what it is, who it is, and
what it's feeling, the design works. If it becomes a blob, no amount of detail on top
will save it. Characters with lasting appeal — Mickey, Bugs, Jerry — have silhouettes
you'd recognise on a keyring.

This isn't an aesthetic preference. The audience reads a shape in a fraction of a
second, especially at flipbook speed, where each drawing is on screen for under a
tenth of a second. Detail below that threshold is invisible; shape is not.

### Appeal has three separate layers

1. **Visual** — proportions, silhouette, one distinctive feature you could describe over the phone.
2. **Emotional** — the face and body read a feeling instantly, so you can empathise.
3. **Personality** — traits and quirks that stay consistent, so the character becomes predictable in a satisfying way.

### Perfect characters are boring

The most repeated point across every appeal article: flaws are what make a character
watchable. A character who always wins has no hook, because there's no question to
answer. **The want plus the obstacle is the hook** — you keep watching to find out
whether they get the thing.

This is also why a chase is such durable material. The want is legible in one frame,
and the obstacle is right there in front of you.

### Why appeal works at all

Human brains are built to scan faces and body language constantly and involuntarily.
Animation takes those cues and amplifies them past life-size, so the audience reads
them without effort. Appeal is essentially hijacking hardware you already have.

---

## Part 3 — What this means for the flipbook in this repo

Applying the above to `flipbook.html` as it currently stands:

**What already works.** The chase is a legible want with a visible obstacle, which is
the hook doing its job. The cat and mouse have different silhouettes and different
sizes, which is the comic pair. The near-miss on page 30 is a violation (he almost
gets him) that is obviously benign (nothing bad happens).

**The biggest missing thing: there is no pause.** All 30 pages run at an even ~82ms.
Nothing is held. By the theory above, that means there is no beat where a laugh could
land. The single highest-value change would be to hold the near-miss for several pages
instead of one — the cat's paw an inch from the tail, three or four pages of almost —
before the mouse escapes.

**No anticipation beat.** The lunge happens without a wind-up. Two or three pages of
the cat gathering himself, crouching, ears flat, *before* he launches, would make the
lunge read as a decision rather than an event.

**No reaction, no cost.** The cat misses and nothing happens to him. Benign violation
says the comedy is the injury that costs nothing — so he should faceplant, slide, and
sit up looking foolish. Right now the book ends on the attempt, not the failure, and
the failure is the funnier half.

**Repetition is unused.** Thirty pages is enough for three failed lunges of increasing
desperation, which would set a rule and then break it.

**Silhouette check not yet done.** Worth filling the cat solid black and confirming he
still reads as a cat and not a loaf of bread on legs.

---

## Part 4 — Repositories worth having

| Repo | What it is | Why |
| --- | --- | --- |
| [dylantarre/animation-principles](https://github.com/dylantarre/animation-principles) | Disney's 12 principles as Claude Code skills. MIT. | Covers timing, anticipation, exaggeration and appeal — every lever named above. |
| [facebookresearch/AnimatedDrawings](https://github.com/facebookresearch/AnimatedDrawings) | Animates a child's drawing with real motion-capture. MIT, Python. Archived Sept 2025, still runs. | The gap between hand-coded motion and motion that reads as alive. |
| [LottieFiles/motion-design-skill](https://github.com/lottiefiles/motion-design-skill) | Timing, easing and choreography for AI agents. | The easing curves the principles above depend on. |

**On a "cartoon funnizer":** there isn't one. The nearest thing is
[Stry233/Prompt-to-GPT-3-...-Humor-Generation](https://github.com/Stry233/Prompt-to-GPT-3-Step-by-Step-Thinking-Instructions-for-Humor-Generation),
which implements Joe Toplyn's four-step joke method from *Comedy Writing for
Late-Night TV*. It is worth reading for the method, but it is a research demo with 2
stars, no license file (so no permission to reuse), and it writes **verbal monologue
jokes about news items** — not visual gags. Nothing on GitHub does visual cartoon
comedy. The closest practical substitute is the animation-principles repo, because
exaggeration, anticipation and timing *are* the visual comedy levers.

---

## Sources

- McGraw & Warren, [*Benign Violations: Making Immoral Behavior Funny*](https://journals.sagepub.com/doi/abs/10.1177/0956797610376073), Psychological Science, 2010 — peer-reviewed; the only experimentally tested item here.
- McGraw, [*A brief introduction to the benign violation theory of humor*](https://petermcgraw.org/a-brief-introduction-to-the-benign-violation-theory-of-humor/) — the plain-English version.
- [*The Science Behind What Makes Cartoons Funny*](https://www.toonsmag.com/the-science-behind-what-makes-cartoons-funny/), Toons Mag — a blog; names the three classic theories but cites no research.
- [*Comedic Timing in Animation*](https://www.animationmentor.com/blog/comedic-timing-in-animation-a-student-showcase-behind-the-scenes/), Animation Mentor — practitioner account of timing.
- [*Animation for Comedy: Art of Timing and Visual Gags*](https://educationalvoice.co.uk/animation-for-comedy/) — setup and subversion of expectation.
- [*Retiming for Comedy*](http://comedyforanimators.com/2020/04/27/retiming-for-comedy-2/), Comedy For Animators — was returning HTTP 503 when checked, so it is listed unread.
- [John K, *Modern Comedy Timing VS Classic Comedy Timing*](http://johnkstuff.blogspot.com/2007/08/modern-comedy-timing-vs-classic-comedy.html) — opinionated but from someone who did the work.
- [*Appeal in Animation*](https://blog.animschool.edu/2024/06/07/appeal-in-animation/), AnimSchool — silhouette and readability.
- [*Appeal in Animation: The Secret Principle Behind Memorable Characters*](https://prolificstudio.co/blog/appeal-in-animation/) — the three layers of appeal.
- [*The Principle of Appeal in Animation*](https://pixune.com/blog/the-principle-of-appeal-in-animation/) — flaws and quirks.
