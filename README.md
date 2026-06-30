# Hmm 🤔

**The ultimate prompting framework.**

`hmm` is a tiny workflow for turning AI coding agents into something closer to a pair programmer: discuss first, align on intent, then build.

The repo might look like a joke — and honestly, it kind of is.

## Why

Ever had a model confidently build something adjacent to what you asked for,
but not actually what you meant? `hmm` is for getting buy-in before
implementation starts. You refine your own understanding, the agent refines its
understanding, and the result becomes much less surprising.

Plans are useful, but starting with a plan can create its own loop. You ask for
one change, the whole plan shifts, and now you're reviewing again. And again. It
shouldn't be like this. Discuss first, get aligned, _then_ ask for a plan.

Think of it as the friendly counterpart to Matt Pocock's
[_Grilling_](https://github.com/mattpocock/skills/blob/main/skills/productivity/grilling/SKILL.md):
same goal of stress-testing your idea, opposite temperament. If you'd rather
have a conversation than an interrogation, this is for you.

You don't need a perfect prompt. Start vague and see how it lands. Ask a
follow-up if the direction is mostly right, or start over if it isn't. Forget
"as a senior software engineer" and "make no mistakes." Find the balance that
works for your project.

Less is more. Too many tools and instructions confuse models, and some
frameworks add thousands of tokens before you've even said what you want. The
prompt is 4 tokens\*. Zero learning curve. You might even memorize it instead of
installing it.

This is made for engineers. You're in control of your context. You're in
charge, not the agent.

<sub>\* Per the OpenAI tokenizer</sub>

## The workflow

It's one command, run manually. Not a skill the model invokes on its own — a
command you choose to fire.

> ⚠️ Stay in **agent mode**, not plan mode. The harness might nudge you to
> switch to plan mode. Don't. This whole thing happens in agent mode.

Instead of asking:

```text
Build X
```

You ask:

```text
I want to build X /hmm
```

The agent switches into a pair-programming mode: it explores the codebase and
comes back with an opinion. Now read it. Does it match your goal? Did it
surface something you didn't know? Do you agree with what it suggests?

Ask a follow-up:

```text
are you sure about Y? Maybe we can reuse Z for that? /hmm
```

Continue until you're aligned. Then just say:

```text
ok, build
```

That's it.

## How it works

The entire skill is one line:

> Let's discuss before implementing.

That sentence is the whole framework. That's all it takes to get the model into pair-programming mode.

The other half is on you: **describe an intention, not an action.** Say
"I want to build X," not "Build X." If you say "Build X /hmm" you've given the
model a mixed signal — should it build, or discuss? Be explicit.

That's all you need.

## Tips

- Disable the question/clarification tool, if your harness has one.
- Disable auto-switch to plan mode.
- Find the model that matches your vibe. I like the responses from gpt-5.5
  medium. Try the same prompt across a few models and see which one you enjoy
  working with.

## Install

### Claude Code

```sh
npx skills add tumenbaev/hmm --skill hmm --agent claude-code --global
```

Use:

```text
/hmm I want to build X
```

### Cursor

```sh
npx skills add tumenbaev/hmm --skill hmm --agent cursor --global
```

Use:

```text
/hmm I want to build X
```

### OpenCode

Install as a native OpenCode command:

```sh
mkdir -p ~/.config/opencode/commands
curl -fsSL https://raw.githubusercontent.com/tumenbaev/hmm/main/commands/opencode/hmm.md \
  -o ~/.config/opencode/commands/hmm.md
```

Use:

```text
/hmm I want to build X
```
