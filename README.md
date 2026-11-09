# Skills

My agent skills for Claude Code. Each skill is a folder with a `SKILL.md` that tells the agent when to use it and how.

## Skills

### [Writing](./skills/writing/README.md)

- **[blog-writer](./skills/writing/blog-writer/SKILL.md)**: Writes personal blog posts from your own experience, in plain words, told as a story with honest results.

## Installation

With [skills.sh](https://skills.sh):

```bash
npx skills@latest add alramdein/skills
```

Or by hand, for Claude Code:

```bash
git clone git@github.com:alramdein/skills.git
ln -s "$PWD/skills/skills/writing/blog-writer" ~/.claude/skills/blog-writer
```

## Layout

```
skills/
└── <category>/
    ├── README.md        # what's in this category
    └── <skill>/
        ├── SKILL.md
        └── references/  # optional, loaded when the skill needs them
```
