# LLM Council — a Claude Code skill

Run any question, idea, or decision through a council of 5 AI advisors who independently analyze it, peer-review each other anonymously, and synthesize a final verdict.

Based on [Andrej Karpathy's LLM Council](https://github.com/karpathy/llm-council) methodology, adapted to run inside Claude Code using sub-agents with different thinking lenses instead of different models.

## What it does

You ask one AI a question, you get one answer. That answer might be great. It might be mid. You have no way to tell because you only saw one perspective.

The council fixes this. It runs your question through 5 independent advisors, each thinking from a fundamentally different angle. They review each other's work. A chairman synthesizes everything into a final recommendation that tells you where the advisors agree, where they clash, and what you should actually do.

## When to use it

Good council questions:
- "Should I launch a $97 workshop or a $497 course?"
- "Which of these 3 positioning angles is strongest?"
- "I'm thinking of pivoting from X to Y. Am I crazy?"
- "Here's my landing page copy. What's weak?"

Bad council questions:
- "What's the capital of France?" (one right answer)
- "Write me a tweet" (creation task, not a decision)
- "Summarize this article" (processing task, not judgment)

## Install

Drop the `SKILL.md` file into your Claude Code skills directory:

```bash
mkdir -p ~/.claude/skills/llm-council
curl -fsSL https://raw.githubusercontent.com/aiwithremy/claude-skills-llm-council/main/SKILL.md -o ~/.claude/skills/llm-council/SKILL.md
```

Or clone the repo:

```bash
git clone https://github.com/aiwithremy/claude-skills-llm-council.git ~/.claude/skills/llm-council
```

Restart Claude Code and the skill will be auto-discovered.

## Use it

In any Claude Code session, just say:

- "council this"
- "run the council on [your question]"
- "pressure-test this"
- "stress-test this"

Claude will spin up the 5 advisors, run the peer review, and deliver the chairman's verdict.

## License

MIT — use it, modify it, share it.
