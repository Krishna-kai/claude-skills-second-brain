# skills/

Skills are extra, repeatable workflows on top of the core wiki workflows (ingest, query, lint). Each one
is a short markdown file the agent follows when you ask for it.

Four ship with the kit:

- `research.md` - investigate a topic across sources and write the findings into the wiki.
- `deep-search.md` - a thorough, current-information sweep: several angles, several sources, plus your wiki,
  freshness checked. For "what is the latest on X." Works for any domain.
- `report.md` - turn the wiki into a clear, sourced report.
- `skill-creator.md` - make a new skill for a task you repeat.

You can add your own. Just say "make me a skill that does X" and the `skill-creator` skill writes a new one
here. A skill is a short markdown file named for the task, with a few steps.

(This "skills for Claude Code" idea is Cole Medin's, from second-brain-skills. See the README credits.)

## Optional: deeper web search

The `research` and `deep-search` skills work out of the box with Claude Code's built-in web search. No
setup needed.

Want deeper, fresher, multi-source research? Add a dedicated search tool (Tavily has a free tier with no
card; students get more) through Docker's MCP hub, and `deep-search` will use it automatically. Full steps,
with the current free-tier facts, are in [`docs/deeper-search.md`](../docs/deeper-search.md).

All optional. The brain works fully without any of this.
