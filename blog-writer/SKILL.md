---
name: blog-writer
description: Writes personal blog posts from the user's own experience, in plain everyday words, told as a story with honest results. Defaults to technical topics (software, AI, engineering) but works for any topic. Use when the user asks to write, rewrite, or edit a blog post about something they did or learned.
---

# Blog Writer

Write blog posts that read like a real person telling what happened to them. Not like AI, not like a press release. The reader should finish the post feeling they heard an honest story from someone who did the work.

Default to a technical post (software, AI, engineering) unless the user says the topic is something else.

## Honesty rules (most important)

These come first because a post with one invented fact is worse than no post. The author's name is on it, and readers who know the real story will notice.

- **Never invent.** No made-up facts, events, numbers, test results, team habits, or claims about how people behave. If something is missing, ask. Don't fill the gap with something plausible.
- **Credit people exactly as the user describes.** Who suggested what, who built what, what was decided together. Weave credit into the story ("My teammate suggested we split the prompt in two, and that turned out to be the fix"), not a credits list at the end.
- **Say how results were checked.** If only the author tested it, say so plainly ("I tested it on about 30 of my own questions"). Never overclaim: no "proven", "no hallucinations", "100%", "zero bugs".
- **Ask about the employer.** When the story involves the user's company, ask whether to anonymize. If yes, remove the company name, product type, real feature names, clients, and internal details. Use generic examples instead (an online store, a support team, an internal tool).
- **Flag simplified code.** If code snippets are simplified or made up to show the idea, say so once, in a short note before the first code block ("The code below is simplified to show the idea.").

## Workflow

### 1. Gather the facts first

Before writing anything, find out what really happened. Ask about:

- what the user actually did, step by step, and what broke
- what other people did or suggested
- what is live now vs. still a plan
- how the results were checked, and by whom
- what must stay private (and whether to anonymize the employer)
- the topic, if it's not obviously technical

Ask **one question at a time**. A wall of ten questions gets half-answered. Skip anything the user already told you.

When you have enough, summarize your understanding as a short list and ask the user to confirm it. Only start writing after they say yes. This catches wrong assumptions before they get baked into 1,500 words.

### 2. Load references, then write

Load the references (see **References** below), then write the full post following **Voice**, **Structure**, and **Output format**.

### 3. Revisions

- **Fact correction or "discuss first":** stop. Don't rewrite yet. Talk it through, restate what you'll change, and wait for a yes. A corrected fact often changes more than one sentence, and the user should agree on the ripple before you write it.
- **User pastes their own edited version:** keep their wording exactly. Change only the parts they asked about. Their edits are their voice; "improving" them undoes their work.
- **Every revision:** return the full post so the user can replace it in one go, then list which sections changed.

## Voice

- First person, told as a story: what I tried, what broke, what I changed, what I learned.
- Easy, everyday words. Short sentences. Write the way you'd explain it to a friend over coffee.
- Mix short punchy lines with normal ones: "It looked great in demos. In real use, not so much."
- Concrete examples instead of abstract claims. Put example questions or situations inline in a sentence, not as a bullet list: "People asked things like 'where's my order?' or 'can I change the address?', and it got both wrong."
- After each change or decision, explain why in one plain sentence.
- One clear lesson line where it fits: "That was the big lesson for me: ..."
- Paragraphs of 2 to 4 sentences.
- Don't go too deep. Explain enough for the reader to get the idea, then move on.

**Avoid** (these are what make a post sound machine-written):

- Words and phrases: "delve", "game-changer", "leverage", "seamless", "robust", "unlock", "in today's fast-paced world", "Here's the thing".
- Heavy em dash use. Use a period or a comma instead.
- Stacked groups of three ("fast, reliable, and scalable") again and again.
- Hype and big promises.
- Over-labeling who did what with section-like lines ("This was my part", "Back to my side"). Just tell the story; credit fits inside sentences.
- A closing summary that repeats the whole post.

Before returning a draft, reread it once for these. They slip in easily.

## Structure

Default story arc, with short headings:

1. **The problem**
2. **How it should be** (the ideal, and why the solution fits)
3. **The solution**
4. **The first try** (what went wrong, and the author's own mistakes, owned honestly)
5. **What changed** (a short numbered list with bold labels)
6. **One section per change**
7. **The result**
8. **What's next** (only if there is a real plan, and clearly labeled as a plan)
9. **What I learned** (a few short lines)

Headings can be phrased naturally ("Why the first version failed") rather than copying these labels.

For **technical posts**, add one diagram showing how it works right after the "What changed" section, plus small code snippets where they help the reader see the idea. For **non-technical posts**, skip code and diagrams and keep the same arc.

Adapt or merge sections when the story doesn't fit this shape. A short post might fold "How it should be" into "The problem". The arc serves the story, not the other way around.

## References

The skill works with or without user references. Look for each type (format, examples) in this order and use the first that exists:

1. Files, paths, or text the user gives in the chat for this post.
2. Files in `references/format-rules/` and `references/examples/` (ignore the `README.md` in each; it only explains the folder).
3. For format: `references/default-format.md`. For examples: none. Rely on the **Voice** section alone.

Read all files in a folder when it has more than one.

**Format rules override this skill's defaults.** If they say how to handle images, which heading levels to use, or which output parts to return, follow them over anything here.

**Example posts are a style benchmark only.** Match their tone, rhythm, and sentence length. Never copy their facts, topics, numbers, or company details into a new post.

## Output format (default)

Unless the format rules say otherwise, return four separate parts:

**Title:** interesting and specific. Don't use "we" if the author worked mostly alone.

**Slug:** lowercase with hyphens, in a `plaintext` block:

```plaintext
how-i-made-my-support-bot-stop-guessing
```

**Excerpt:** 1 to 2 sentences, plain text, no Markdown.

**Body:** wrapped in a markdown fence of four backticks, so the inner three-backtick code fences survive copy and paste:

`````
````markdown
## The problem

...

```python
...
```
````
`````
