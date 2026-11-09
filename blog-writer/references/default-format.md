# Default format

Used only when no format rules are found in the chat or in `format-rules/`.

## Markdown

- GitHub-flavored Markdown.
- `##` is the top heading level inside the body. The title is returned separately, so the body has no `#` heading.
- `###` for sub-sections only when a section really needs them.
- Bold for the labels in the "What changed" numbered list. Otherwise use bold sparingly.

## Code

- Fenced code blocks with a language tag (`python`, `ts`, `bash`, `json`, ...).
- Keep snippets short: the few lines that show the idea, not a full file.
- If snippets are simplified or invented to illustrate, add one short note before the first code block.

## Diagrams

- Mermaid, in a ```` ```mermaid ```` block.
- One diagram per technical post, right after the "What changed" section.
- Keep it small: the main parts and how data flows between them. Short node labels in plain words.

## Images

- No image placeholders. Don't write `![...](...)` or "[insert screenshot here]".

## Output parts

Return Title, Slug, Excerpt, and Body as described in SKILL.md.
