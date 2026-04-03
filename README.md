# CCA Learning

Learn Anthropic's Claude Certified Architect (CCA) course material with AI as your tutor.

This repository contains CCA course material covering AI fluency, the Claude API, MCP, Claude Code, agent skills, and subagents. Instead of passively reading through lessons, you use Claude Code to work through the material interactively. It reads the lessons, teaches you the concepts, quizzes you, and helps you apply what you learn to real work.

## Getting started

### Prerequisites

- [Claude Code](https://docs.anthropic.com/en/docs/claude-code) installed
- A terminal

### Steps

1. Clone this repo:
   ```
   git clone https://github.com/Quallaa-AI/cca-learning.git
   cd cca-learning
   ```

2. Start Claude Code:
   ```
   claude
   ```

3. Tell it what you want to learn:
   - "Help me learn the AI Fluency Framework" — start with the foundations
   - "Quiz me on tool use" — test your knowledge
   - "Walk me through the MCP course" — go lesson by lesson
   - "I'm building a customer service bot — which course concepts apply?" — learn by doing

That's it. Claude reads the course material, uses the evaluation rubric, and adapts to your level.

## What's in here

### Core courses (5)

Anthropic has two official course lists that don't fully agree. The CPN acceptance email requires 4 courses for partner admission. The CCA exam landing page recommends a different 4 for exam prep. Three overlap. These 5 cover both:

| Course | Lessons | What it covers | Source |
|--------|---------|---------------|--------|
| Introduction to Agent Skills | 6 | Claude Code skills — creating, configuring, sharing, troubleshooting | CPN required |
| Building with the Claude API | 85 | API basics, prompt engineering, tool use, RAG, extended thinking, prompt caching, MCP, agent and workflow patterns | Both |
| Introduction to MCP | 14 | Model Context Protocol — servers, clients, tools, resources, prompts | Both |
| Claude Code in Action | 21 | Context management, planning mode, hooks, custom commands, GitHub integration, the SDK | Both |
| Claude 101 | 14 | What Claude is, core capabilities, projects, artifacts, skills, tools, research mode | CCA recommended |

### Supplemental courses

Additional Anthropic Academy courses that deepen exam-relevant topics:

| Course | Lessons | What it covers |
|--------|---------|---------------|
| AI Fluency Framework Foundations | 15 | The 4D Framework (Delegation, Description, Discernment, Diligence), engagement modes, human-AI collaboration philosophy |
| MCP Advanced Topics | 15 | Sampling, notifications, roots, JSON message types, STDIO and StreamableHTTP transports |
| Introduction to Subagents | 4 | Delegating tasks to isolated agents, built-in and custom subagents, design patterns |
| Introduction to Claude Cowork | 11 | The task loop, plugins, scheduled tasks, file/research workflows, permissions, model selection |

## CCA exam domains

The CCA-F exam tests five domains. Here's how courses map to each:

| Domain | Weight | Core courses | Supplemental |
|--------|--------|-------------|--------------|
| Agentic Architecture & Orchestration | 27% | Building with the Claude API, Agent Skills | Introduction to Subagents |
| Claude Code Configuration & Workflows | 20% | Claude Code in Action, Agent Skills | Claude Cowork |
| Prompt Engineering & Structured Output | 20% | Building with the Claude API | — |
| Tool Design & MCP Integration | 18% | Introduction to MCP, Building with the Claude API | MCP Advanced Topics |
| Context Management & Reliability | 15% | Building with the Claude API, Claude Code in Action | Introduction to Subagents |

## Learning paths

**CCA + CPN prep:** Work through the 5 core courses. Start with Claude 101, then Agent Skills, Building with the Claude API, Introduction to MCP, and Claude Code in Action.

**New to Claude:** Start with Claude 101, then AI Fluency Framework Foundations.

**Building with the API:** Go straight to Building with the Claude API. It's self-contained and hands-on.

**Using Claude Code daily:** Claude Code in Action, then Introduction to Agent Skills, then Introduction to Subagents.

## How it works

The `CLAUDE.md` file in this repo instructs Claude to act as a tutor — not a summarizer. It will:
- Teach concepts using the lesson files, not just repeat them
- Quiz you with scenario-based questions drawn from the evaluation rubric
- Help you apply concepts to your real work
- Track what you've covered and build on it

The `rubric.yaml` file contains evaluation criteria for many modules. Claude uses this to assess your understanding meaningfully. For courses without rubric coverage, it quizzes based on lesson content directly.

## License

Course content is Copyright 2025 Rick Dakan, Joseph Feller, and Anthropic. Released under the [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/) license. Based on The AI Fluency Framework by Dakan and Feller. Supported in part by the Higher Education Authority, Ireland, through the National Forum for the Enhancement of Teaching and Learning.
