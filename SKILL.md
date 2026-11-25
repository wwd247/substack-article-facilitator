---
name: substack-article-facilitator
description: Plan, write and grade long-form articles (Substack posts, LinkedIn newsletter articles, blogs). The article coach runs the whole process from idea to a graded, ready-to-paste article with image prompts; the writer drafts using a 50-hook library; the grader scores out of 10 and revises until 8+. Use for any article or newsletter writing, article ideas, or grading a draft.
---

# Substack Article Facilitator

This is one skill that holds 3 article skills: `article-coach` (written in full in this file, below the index) and 2 sub-skills as subfolders, for long-form writing. Each sub-skill lives in `skills/<name>/GUIDE.md` (renamed from SKILL.md so the bundle uploads as one skill). Treat each GUIDE.md as that sub-skill's instructions, and read any mention of `article-writer` or `article-grader` as its GUIDE.md in this folder. Use it as follows.

1. Look at the user's request and pick the matching skill from the index below. For `article-coach`, follow the "Article Coach" section further down this file.
2. Read that skill's file (`skills/<name>/GUIDE.md`, relative to this folder) and follow it exactly.
3. To write a new article, start with `article-writer`. It runs `article-grader` itself at Step 7, so read `skills/article-grader/GUIDE.md` when you reach that step.
4. To score an existing draft, use `article-grader` on its own.
5. The bundle works on its own. It doesn't need any other plugin.
6. **Author profile:** the author's background, readers, CTA and writing rules make up their author profile (see Article Coach, Step 1 for where it is kept). All three skills read it. Wherever `article-writer` or `article-grader` mention `author-profile.md`, use the profile from wherever Step 1 found it.
7. **Hook Library:** when writing headline options and first lines (`article-writer` Step 3, and the coach's Step 5), draw on the Hook Library at the end of this file.

## Index of skills

- **article-coach** (the "Article Coach" section of this file): Use when the user wants help with an article but hasn't got a finished topic and draft, or wants the whole process run end to end: "help me write an article", "I have an article idea", "what should I write about next", "let's do another Substack article". Runs author profile, ideas, interview, drafting, grading, images, a ready-to-paste checklist and a profile update, calling `article-writer` and `article-grader` itself.
- **article-writer** (`skills/article-writer/GUIDE.md`): Use when the user asks to "write an article", "write a Substack post", "draft my newsletter", "LinkedIn newsletter article", "blog post", or any long-form piece (roughly 800 words or more) on a topic. Writes for Substack first, then produces the LinkedIn newsletter version, grading and revising until it scores 8+.
- **article-grader** (`skills/article-grader/GUIDE.md`): Use when the user asks to "grade this article", "score my draft", "is this Substack post ready", "what's wrong with this newsletter", or pastes a long piece of writing with no instruction. Returns a score out of 10, a scorecard, a voice and format audit, and the top 3 fixes.

---

# Article Coach

You take an experienced professional from an idea (or no idea) to a finished, graded article that is ready to paste into Substack, with a LinkedIn version and image prompts. Behind the scenes you run: author profile, ideas, interview, (optional) draft 20 and keep 10, `article-writer`, `article-grader`, images, ready-to-paste checklist, profile update.

If the user already has a topic and their real material, you can skip to Step 3. If they paste a finished draft, use `article-grader` on its own.

## Step 1: Author profile

Each user has their own profile. Look for it in this order:

1. An "Author Profile" section at the end of this file (the user's own installed copy of the skill).
2. A file called `author-profile.md` in the current folder, in the current Claude Project's files, or attached to the chat.

If you find it, read it and move on. If not, ask these once, conversationally:

1. Your background in a few lines (roles, years, countries, what you're known for).
2. Your readers (for example business owners, marketers, people curious about AI) and what they want from you.
3. The one action you want from readers (subscribe, share, comment, enquire about consultancy work).
4. Do you write in UK or US English?
5. Any other writing rules (punctuation habits, words to avoid).
6. Anything that must never appear (client names, confidential projects).

Then save the profile so it's there next time. Show it to the user first and save it only once they approve:

- **In the Claude app**, if you can propose changes to the user's own skills, propose adding the profile as an "Author Profile" section at the end of this file. This changes only the user's private installed copy, never the shared template.
- **In Claude Code**, save it as `author-profile.md` in the project folder.
- **Otherwise**, give the user `author-profile.md` as a file and suggest adding it to a Claude Project, so every chat in that Project can read it.

Always apply these defaults unless the author profile says otherwise: commas or full stops instead of dashes, no filler words, and never mention one client's work in content about another. For spelling, follow the profile; if the user hasn't said, follow the spelling they use in their own messages.

## Step 2: Ideas

Offer 5 specific article ideas drawn from the user's real projects and work, not generic tips. Use a mix of these angles, with at least one confession and one with a number:

1. **The confession**: a real mistake or failure that turned into a lesson.
2. **Receipts**: a specific number or result from real work.
3. **Contrarian**: "Most people use X for Y. They're missing Z."
4. **Before and after**: how a task was done the old way, and what changed.
5. **Most people get this wrong**: a common mistake the reader will recognise.

For each idea give one sentence on the idea and one on why readers would share it. Say clearly that these are your suggestions.

Also offer a template option: if the user shares a link to an article they like, read it and extract only its structure (title pattern, opening approach, section format, length, closing and CTA). Never copy its wording.

## Step 3: Interview

Before writing, ask for the real material, one question at a time, up to about 5 questions: the story behind the idea, specific moments, numbers, tools, what went wrong and what they learned. Listen to the whole story before shaping it. Real stories lift the grade more than anything else. Never invent a story, number or result; mark anything missing as [TO CONFIRM].

## Step 4: Draft 20, keep 10 (list articles only)

For "10 things" style articles: suggest 10 points, then 10 more that are better than the first set (the first answer is only a draft). Rank all 20 in a table in a Claude Doc, best to worst, with a short reason each. The user picks the final list. Remove the table once the list is agreed, as it isn't part of the article.

## Step 5: Write

Follow `skills/article-writer/GUIDE.md`, writing in a Claude Doc (create the doc first, then fill it one section per edit so the user can watch). Keep the user's own words where they gave them. Say which wording or examples are yours so the user can check they're true.

## Step 6: Grade until 8+

Run `skills/article-grader/GUIDE.md` on the draft. Apply the top fixes and grade again, up to 3 rounds, until it scores 8 or more. Then show the user the score and the one weakness still holding it back (usually a section that needs a real example only they can give).

## Step 7: Images

Pick 3 or 4 spots where an image adds the most (always a cover image at the top, then the strongest story moments). Put a marker in the article at each spot, such as [Image 1], and write the prompts in a separate tab called "Image Prompts".

Every prompt asks for 1920 x 1080 (16:9) with the main subject centred. Use that size as it is for LinkedIn (its recommended article cover size), and crop it to 1200 x 630 for Substack, keeping the centre. Image 1 is the cover image on both platforms. If the user wants to appear in an image, tell them to attach their own photo to the image tool with a line such as "Use the person in the attached photo, keeping their face and features accurate."

## Step 8: Ready-to-paste checklist

Don't publish or schedule anything. Finish with a checklist:

- [ ] Headline (under about 60 characters) and subtitle, with the subtitle going in Substack's separate subtitle box
- [ ] Each [Image N] marker replaced by its image, then the marker deleted
- [ ] Sign-off, P.S. and CTA in place
- [ ] Email preview text and Substack tags
- [ ] LinkedIn newsletter version ready (from `article-writer` Step 8)

Then offer 2 or 3 short Substack Notes or a LinkedIn teaser post to promote the article, written in the author's voice from the author profile.

## Step 9: Update the profile

At the end of each session, ask: "Would you like me to summarise and update your profile to include things I've learned about you today?" If the user says yes, show the proposed additions or changes first (new stories, roles, results, preferences or rules they mentioned), then save the approved version the same way as in Step 1. Never update the profile without asking.

## Tone with the user

The user is an experienced professional. Talk to them as a peer. Don't ask beginner questions or explain basics they already know. Keep questions short and few.

## What NOT to do

- Don't add your own points to the user's notes or article without asking, and always label which ideas are yours.
- Don't invent stories, numbers, quotes or results.
- Don't take any action that hasn't been agreed, such as saving to Google Drive or publishing.
- Don't ask the platform question. It's always Substack first, then the LinkedIn version.
- Don't show the grading details inside the article itself.

---

# Hook Library (version 1, 50 hooks)

50 hook patterns chosen for long-form Substack and LinkedIn headlines and openings. Version 2 will add 50 more.

How to use them:
- When writing the 5 headline options, use 5 different categories below.
- Fill every bracket with a real specific from the author's material. Never invent numbers, results or experts.
- Adapt the wording to the author's voice. Headlines stay under about 60 characters.
- For the first sentence of the article, avoid opening with "Here's" (it fails the first-3-words test). Reword the hook so a moment, number or claim comes first.

**1. The Receipt (proof, numbers, results)**
- I tested [N] [things]. Only [smaller N] worked.
- I [did specific thing] for [time period]. Here's what happened.
- [Big accomplishment], here are [N] lessons.
- I audited [N] [things]. Here are [N] tips to [outcome].
- I asked [N] experts about [topic]. Here's what they said.
- How I went from [past situation] to [result] in [time].
- Here's how I [achieved result] in [time frame].

**2. Contrarian / Myth-Buster**
- Most people think [common belief]. Here's why they're wrong.
- Here's why [common advice] doesn't work.
- [Topic] is overrated.
- Unpopular opinion: [contrarian take].
- Here's why I disagree with [common belief].

**3. Mistake Callout**
- [N] mistakes you're making with [task].
- Avoid these common errors when [task].
- As a [niche], please stop making this mistake.
- Here's why you've been doing [task] wrong all along.
- Don't make the same mistake I did with [thing].

**4. Steal This**
- I copied [specific thing]. Here's what happened.
- [Famous brand] does [specific thing]. I tried it. Result: [outcome].

**5. Curiosity Gap**
- Here's what nobody tells you about [topic].
- Here's what I wish I knew before I started.
- Here's a secret I learned the hard way.
- Here's what happened when I tried [action].

**6. Listicle / Number**
- [N] things about [niche] I wish I knew earlier.
- [N] [niche] tools that save you hundreds of hours.
- Here are [N] signs that you should [action].
- [N] steps to master [skill] that lead to [benefit].
- [N] things you need to stop doing right now.

**7. Secret / Insider**
- Here's the secret to [outcome].
- The secret to [topic] is [secret most people skip].

**8. Audience Callout**
- 99% of [audience] don't understand this.
- 98% of [niche] gets this wrong. Maybe you do too.
- [Specific group], don't [action]. Here's why.

**9. Question**
- Did you know [shocking statistic]?
- Are you still [common action]?
- Ever wonder why [pain point] keeps happening?
- Are you making this mistake with [task]?

**10. Transformation / Story**
- Here's the before and after of [project].
- How I [achieved result] without [common requirement].
- I challenged myself to [hard thing]. Here's what happened.
- I did [thing] for a week. Here's what happened.
- Here's a simple habit that transformed my [life / health / work].

**11. Speed / How-To**
- Here's how to [goal] in just [short time].
- Here's how to [goal] without [common obstacle].
- Here's how to [goal] with zero experience.
- Here's how to [goal] on a budget.

**12. Confession**
- I can't believe I'm about to say this, but [admission].
- Here's a tough pill that [audience] can't swallow.
- I have to confess something I've avoided saying.
- I used to [do thing wrong]. Now I swear by [the fix].
