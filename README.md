# Readable prose

An agent skill that makes English easier to read on the first pass. It helps the agent spot seven patterns that slow readers down, including long gaps between a subject and its verb and strings of three or more nouns.

> Before: The fix the reviewer suggested broke the tests.
>
> After: The reviewer suggested a fix. It broke the tests.

## Install

### Claude on the web or desktop

1. Download [readable-prose.zip](https://github.com/yym0329/readable-prose/releases/latest/download/readable-prose.zip).
2. Open **Customize → Skills → + → Create skill → Upload a skill** and select the ZIP. [Claude's upload guide](https://support.claude.com/en/articles/12512180-use-skills-in-claude)
3. Ask Claude to use Readable prose on a draft.

### Claude Code

```sh
mkdir -p ~/.claude/skills
git clone https://github.com/yym0329/readable-prose.git ~/.claude/skills/readable-prose
```

Open Claude Code and type `/readable-prose`. [Claude Code skills guide](https://code.claude.com/docs/en/skills)

### Codex

```sh
mkdir -p ~/.agents/skills
git clone https://github.com/yym0329/readable-prose.git ~/.agents/skills/readable-prose
```

Open Codex and type `$readable-prose`.

## Research

The [skill instructions](SKILL.md) adapt findings from Thomas Hikaru Clark, Matias B. Martin, and Kyle Mahowald. [Why is AI-generated language so hard to understand?](https://arxiv.org/abs/2610.29162)
