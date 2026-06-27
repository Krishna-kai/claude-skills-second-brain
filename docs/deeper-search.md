# Deeper search with Docker and MCP (optional)

Your `research` and `deep-search` skills already work with Claude's built-in web search. **You do not need
anything on this page to start.** This is the optional upgrade: give Claude a dedicated search tool so its
research goes deeper and stays current. You set it up once, and the `deep-search` skill already knows to use
it when it is there.

## The idea: Docker as the hub for tools

MCP (the Model Context Protocol) is how Claude uses outside tools, like a web-search service. You could wire
each tool up by hand, but that means installing runtimes and pasting keys into config files.

Docker's **MCP Toolkit** is the easier way: a hub. It is a catalog of ready-made tools, each one running in
its own small container, that you switch on and connect to Claude in a couple of clicks. Add a tool to the
hub, and Claude can use it. That is the "Docker hub" for your second brain: the place its tools live.

## What you need

- **Docker Desktop** (free for personal use). https://www.docker.com
- **Claude Code** (you already have it).
- **A free search API key.** Tavily is the pick: **1,000 searches a month, free, no credit card**, and the
  count resets on the 1st. **Students get 4 months of 4,000 a month free.** https://tavily.com
  - Why Tavily and not the others: Microsoft retired the Bing Search API in August 2025, and Brave dropped
    its free tier in 2026 (it now needs a card). Tavily is the simplest genuinely-free option today.

## Set it up (about five minutes)

Docker's own steps are the ones to follow, because the exact menus change between versions. The official
guide is short and current:

**https://www.docker.com/blog/add-mcp-servers-to-claude-code-with-mcp-toolkit**

The shape of it:

1. Install Docker Desktop and open it. Turn on the **MCP Toolkit** (in Settings, under beta features).
2. In the MCP Toolkit **Catalog**, find **Tavily**, add it, and paste your free Tavily key when asked.
3. **Connect Claude Code.** Docker Desktop has a one-click "Connect" for Claude Code; it writes an
   `.mcp.json` in your folder that points Claude at the Docker MCP gateway. (There is a command-line way too,
   in the guide.)
4. **Restart Claude Code**, then type `/mcp`. You should see the Docker gateway listed; its tools show up
   under the name `MCP_DOCKER`.

## Use it

Nothing new to learn. Just ask as you already do:

> "deep-search the latest on solid-state batteries."

The `deep-search` skill says: "if a search MCP is set up, use it." So Claude now pulls from Tavily for
fresher, deeper results, then saves the findings to your wiki with sources, exactly as before. The
`research` skill benefits the same way.

## If you would rather not

You do not have to do any of this. Built-in search is enough to begin with, and every part of the kit works
without it. Add the hub only when you want your research to go deeper.

---

Sources, checked June 2026: Tavily free tier and student plan, https://docs.tavily.com/documentation/api-credits .
Docker MCP Toolkit with Claude Code, https://www.docker.com/blog/add-mcp-servers-to-claude-code-with-mcp-toolkit .
Bing Search API retirement (11 August 2025), https://learn.microsoft.com/en-us/lifecycle/announcements/bing-search-api-retirement .
