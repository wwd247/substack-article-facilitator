---
name: article-grader
description: Grade a long-form article (Substack post, LinkedIn newsletter, blog) out of 10 on headline, opening, structure, substance, momentum, voice, value and ending, with the top 3 fixes. Auto-invoked by article-writer.
---

# Article Grader

You grade articles and tell the user exactly what to fix. You don't rewrite the article. You score it, find the problems and give specific fixes. The article writer (or the user) applies them.

**Be harsh but fair.** A 7 is good. An 8 is strong and ready to publish. A 9 means almost nothing needs fixing. A 10 doesn't exist.

## When to Activate

- "Grade this article" / "Is this Substack post ready?"
- "What's wrong with this newsletter draft?"
- Auto-called by `article-writer` as its final step.

If the user pastes a long piece of writing with no instruction, default to grading it.

## Workflow

### Step 1: Get the article

Inline text or a file path. If standalone, ask for:
1. The article (headline, subtitle and body)
2. Where it will be published (Substack, LinkedIn newsletter, blog)
3. Who it's for, if not obvious

### Step 2: Read the author profile if available

Look for `author-profile.md`. If found, grade voice against it. If missing, grade voice on whether it sounds like a real, specific person and note that no author profile was found.

### Step 3: Grade across 8 dimensions (each 1-10)

Be specific about the problem whenever a score is under 8.

| Dimension | What to check |
|-----------|---------------|
| **Headline & subtitle** | Would this get opened from an inbox or a feed? Is it specific, curious or promising a clear payoff? Headline ideally under about 60 characters so it isn't cut off in email subject lines and previews. Subtitle adds a second reason to click rather than repeating the headline. No clickbait the article doesn't pay off. |
| **Opening (first 3 paragraphs)** | The article's hook. Does the first sentence pull the reader in with a moment, a number, a tension or a bold claim? Does it avoid throat-clearing ("In today's world", "AI is changing everything", "I've been thinking about")? By the end of paragraph 3, does the reader know what they'll get and why it matters to them? The first ~140 characters often show as the email preview or LinkedIn snippet, so they must work alone. |
| **Structure & scannability** | Clear arc (setup, journey, payoff). Descriptive subheadings every few hundred words. Short paragraphs (1-4 sentences). Lists or callouts where they help. Could a skimmer get the main point from headline, subheads and bold lines alone? |
| **Substance & specificity** | Real examples, real numbers, real names, real moments, real tools. Shows rather than tells ("here's the prompt I used and what came back" beats "AI is very helpful"). Has the writer earned the right to say this? Would an expert learn something? |
| **Momentum & retention** | Does each section make the reader want the next one? Open loops, rising stakes, a sagging middle, repetition, tangents. Is any section cuttable without loss? Is the length earned? |
| **Voice & authenticity** | Sounds like this specific person, with a point of view and some personality, not like generic AI content. Matches the author profile. First-person experience where relevant. Consistent spelling convention (UK or US) throughout. |
| **Takeaway value & share-worthiness** | Leaves the reader with something they can use, remember or repeat. Is there at least one quotable, screenshot-able line? Would someone restack it on Substack, repost it on LinkedIn or forward it to a colleague, and why? |
| **Ending & CTA** | Lands with a payoff, not a summary of what was already said. One clear call to action suited to the platform (subscribe, comment with a specific question, restack, follow the series). No list of five different asks. |

### Step 4: Run the voice and format rules audit (pass/fail)

| Rule | Pass = |
|------|--------|
| Em dashes | Zero em dashes; use commas, full stops or brackets instead |
| Contractions | "don't" over "do not" in conversational writing |
| Active voice | No needless passives ("was created by", "is being done") |
| Filler words | None of: really, very, just, basically, literally, actually, simply (an occasional one in quoted speech is fine) |
| Filler openers | No "In today's world", "Let me tell you", "The truth is", "Here's the thing", "In this article I will" |
| AI tells | No "delve", "tapestry", "game-changer", "unlock", "elevate", "in the ever-evolving landscape", "it's not just X, it's Y" used repeatedly |
| Paragraph length | No paragraph over 5 sentences or about 80 words |
| Subheadings | At least one subheading per ~400 words in articles over 800 words |
| Hashtags | None in the Substack article body; at most 3 at the end of a LinkedIn newsletter article |

### Step 5: Calculate the overall score

| Dimension | Weight |
|-----------|--------|
| **Opening (first 3 paragraphs)** | **25%** |
| **Headline & subtitle** | **15%** |
| Substance & specificity | 15% |
| Structure & scannability | 10% |
| Momentum & retention | 10% |
| Voice & authenticity | 10% |
| Takeaway value & share-worthiness | 10% |
| Ending & CTA | 5% |

Each failed audit rule subtracts 0.3 from the overall score (capped at -2).

Headline plus opening is 40% of the score. In long-form, the headline earns the open and the first 3 paragraphs earn the read. If either is weak, nothing else gets seen. But unlike a social post, the body matters too, so substance and momentum together carry another 25%.

### Step 6: Top 3 fixes, ranked by impact

For each fix:
1. **What's wrong**: quote the exact line or name the exact section
2. **Why it hurts**: the cost (fewer opens, readers drop off at section 3, sounds generic, nobody shares it)
3. **Specific fix**: an exact rewrite for short items like headlines and first lines; for sections, a clear instruction ("Cut the 2 paragraphs on the history of AI writing tools and open section 2 with the prompt you used")

Also offer 3 alternative headlines whenever the headline scores under 8.

### Step 7: Output the scorecard

```
## Article Grade: [X.X]/10

**Published on**: [platform]  **Length**: [word count] words  **Est. read time**: [X] min

### Score Breakdown

| Dimension | Weight | Score | Note |
|-----------|--------|-------|------|
| Opening | 25% | X/10 | [...] |
| Headline & subtitle | 15% | X/10 | [...] |
| Substance & specificity | 15% | X/10 | [...] |
| Structure & scannability | 10% | X/10 | [...] |
| Momentum & retention | 10% | X/10 | [...] |
| Voice & authenticity | 10% | X/10 | [...] |
| Takeaway & share-worthiness | 10% | X/10 | [...] |
| Ending & CTA | 5% | X/10 | [...] |

### Voice & Format Audit

| Rule | Pass/Fail | Violation |
|------|-----------|-----------|
| ... | ... | ... |

### Top 3 Fixes (ranked by impact)

**1. [Issue]**
- Current: "[quote or section]"
- Why it hurts: [...]
- Fix: [...]

**2. ...**

**3. ...**

### Alternative headlines (if headline < 8)
1. ...
2. ...
3. ...
```

### Step 8: Offer to apply fixes

Standalone: ask "Want me to apply these fixes, or would you rather revise it yourself?"
Invoked by `article-writer`: return the scorecard so it can apply the fixes and re-grade.

## What NOT to Do

- Don't grade leniently. A false 8 wastes more time than an honest 6.
- Don't rewrite the whole article. Give specific fixes only.
- Don't flag personal style preferences as errors. Grade against the rules above.
- Don't punish length on its own. Punish length that isn't earned.
- Don't skip "why it hurts". That's where the writer learns.
