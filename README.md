# CCA Learning

Learn Anthropic's Claude Certified Associate (CCA) course material with AI as your tutor.

This repository contains the full CCA course catalog — five courses covering AI fluency, the Claude API, MCP, Claude Code, and agent skills. Instead of passively reading through lessons, you use Claude Code to work through the material interactively. It reads the lessons, teaches you the concepts, quizzes you, and helps you apply what you learn to real work.

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

| Course | Lessons | What it covers |
|--------|---------|---------------|
| AI Fluency Framework Foundations | 15 | The 4D Framework (Delegation, Description, Discernment, Diligence), engagement modes, human-AI collaboration philosophy |
| Introduction to Agent Skills | 6 | Claude Code skills — creating, configuring, sharing, and troubleshooting reusable AI behavior |
| Building with the Claude API | 85 | API basics, prompt engineering, tool use, RAG, extended thinking, prompt caching, MCP, agent and workflow patterns |
| Introduction to MCP | 14 | Model Context Protocol — servers, clients, tools, resources, prompts |
| Claude Code in Action | 21 | Context management, planning mode, hooks, custom commands, GitHub integration, the SDK |

## Suggested learning paths

**New to AI collaboration:** Start with AI Fluency Framework Foundations. It gives you the mental models that make everything else click.

**Building with the API:** Go straight to Building with the Claude API. It's self-contained and hands-on.

**Using Claude Code daily:** Start with Claude Code in Action, then Introduction to Agent Skills.

**Want the full picture:** Work through all five in order. The courses build on each other.

## How it works

The `CLAUDE.md` file in this repo instructs Claude to act as a tutor — not a summarizer. It will:
- Teach concepts using the lesson files, not just repeat them
- Quiz you with scenario-based questions drawn from the evaluation rubric
- Help you apply concepts to your real work
- Track what you've covered and build on it

The `rubric.yaml` file contains evaluation criteria for every module across all courses. Claude uses this to assess your understanding meaningfully.

## License

Course content is Copyright 2025 Rick Dakan, Joseph Feller, and Anthropic. Released under the [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/) license. Based on The AI Fluency Framework by Dakan and Feller. Supported in part by the Higher Education Authority, Ireland, through the National Forum for the Enhancement of Teaching and Learning.
