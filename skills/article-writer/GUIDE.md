---
name: article-writer
description: Write a long-form article (Substack post, then LinkedIn newsletter version) from a topic, with a strong headline and opening, then auto-run article-grader and revise until it scores 8+.
---

# Article Writer

You take a topic and return a finished, graded article: headline, subtitle, body with subheadings, and a CTA. Default flow: write for Substack first, then produce the LinkedIn newsletter version and a short LinkedIn teaser post.

## When to Activate

- "Write an article / Substack post / newsletter about X"
- "Draft my LinkedIn newsletter on X"
- Any long-form writing request (roughly 800 words or more) with a topic.

If the topic or the audience is missing, ask. Default platform is Substack, with a LinkedIn newsletter republish.

## Workflow

### Step 1: Load context

1. Look for `author-profile.md`. If missing, run Step 1 of the Article Coach (in the bundle's SKILL.md) to create it, then continue.
2. Confirm in one short message: the topic, the reader (who they are, what they already know), the one thing the reader should walk away with, and the goal (grow subscribers, build authority, sell something later).
3. Gather the raw material before writing: the user's real story, numbers, screenshots, prompts, tools, dates, mistakes and results. Ask for what's missing. Specifics are what make an article worth reading; never invent them. Mark anything unknown as [TO CONFIRM] rather than guessing.

### Step 2: Find the angle

Write the article's promise in one sentence: "After reading this, you'll [know / be able to / see] ___." If you can't, the angle isn't clear yet. Good angles for long-form:

- **Behind the scenes / build in public**: "How I'm using X to do Y, including what went wrong"
- **Receipts**: "I did X for N weeks. Here's what happened"
- **Contrarian**: "Most people use X for Y. They're missing Z"
- **Playbook**: "The exact process I use for X, step by step"
- **Story with a lesson**: a real moment that turns into a takeaway

### Step 3: Headline and opening first (40% of the grade)

1. Write 5 headline options using 5 different categories from the Hook Library at the end of the bundle's SKILL.md. Keep each under about 60 characters. Pick the strongest and write a subtitle that adds a second reason to open.
2. Write 3 different first sentences. Apply the first-3-words test: do the opening words alone create curiosity, tension or a picture? Pick the best.
3. Draft the first 3 paragraphs: hook, why it matters to the reader, what they'll get. Check that the first ~140 characters work alone as an email preview or LinkedIn snippet.

Don't write the body until the headline and opening are strong.

### Step 4: Outline, then draft the body

Outline first: 3-6 sections, each with a descriptive subheading and one job. Then draft section by section.

Body rules:
- **Length**: 1,000-2,500 words is the usual sweet spot; shorter if the idea is small. Length must be earned.
- **Show, don't tell**: real examples, prompts, before-and-after, numbers, screenshots to include (mark as [IMAGE: description]).
- **Short paragraphs**: 1-4 sentences. Vary sentence length for rhythm.
- **Subheadings** every few hundred words, written so a skimmer gets the story from them alone.
- **Momentum**: end each section with a reason to read the next one.
- **One big idea** per article. Save spin-off ideas for future posts and list them for the user at the end.
- **Spelling**: follow the user's convention (UK or US) from the author profile.

### Step 5: Ending and CTA

End with a payoff (the insight, a look ahead, or a line worth quoting), not a recap. Then one CTA:
- **Substack**: subscribe ("I'm documenting the whole process here, subscribe to get the next part"), or a specific comment question, or restack.
- **LinkedIn newsletter**: a specific, slightly polarising question to drive comments, or follow the newsletter.

Avoid vague CTAs like "What do you think?" and stacking several asks.

### Step 6: Apply voice rules

- [ ] Zero em dashes (use commas, full stops or brackets)
- [ ] Contractions used
- [ ] Active voice
- [ ] No filler words (really, very, just, basically, literally, actually, simply)
- [ ] No filler openers or AI tells (delve, game-changer, unlock, elevate, ever-evolving landscape)
- [ ] Reads like a real person who did the thing

### Step 7: Auto-invoke article-grader and revise

Read `../article-grader/GUIDE.md` and grade the draft with it. Apply the top fixes and re-grade. Aim for 8+/10. Stop after 3 revision rounds even if below 8, and tell the user what's holding the score back (usually missing real material only they can provide).

### Step 8: Produce the platform versions

1. **Substack article** (primary): headline, subtitle, body, CTA, plus suggested email preview text and 3-5 Substack tags.
2. **LinkedIn newsletter version**: same article with a LinkedIn-native CTA, an optional line "Originally published on my Substack" with the link if the user wants cross-traffic, and up to 3 hashtags at the end. Suggest a cover image idea (LinkedIn's recommended newsletter cover is 1920 x 1080).
3. **Teaser posts** (optional): offer to write a short LinkedIn post and a Substack Note that promote the article, in the author's voice.

### Step 9: Return the final package

```
**Platform**: Substack (+ LinkedIn newsletter version)
**Angle**: [one sentence promise]
**Quality score**: [X.X/10] after [N] revision rounds
**Length**: [words] words, about [X] min read

---
# [Headline]
### [Subtitle]

[Article]
---

**Email preview text**: ...
**Substack tags**: ...
**LinkedIn version changes**: ...
**Still to confirm**: [any [TO CONFIRM] items]
**Ideas for follow-up articles**: ...
```

## What NOT to Do

- Don't invent stories, numbers, quotes or results. Ask, or mark [TO CONFIRM].
- Don't write 3 full versions for the user to choose from. Pick one; offer headline alternatives only.
- Don't pad to hit a word count.
- Don't put the grading details or angle notes inside the article itself.
