---
module: 12
title: "GitHub integration"
course: claude-code-in-action
topics:
  - GitHub Actions
  - @claude mentions
  - automated PR reviews
  - /install-github-app
---

# GitHub integration

Claude Code offers an official GitHub integration that lets Claude run inside GitHub Actions. This integration provides two main workflows: mention support for issues and pull requests, and automatic pull request reviews.

## Setting Up the Integration

To get started, run `/install-github-app` in Claude. This command walks you through the setup process:

- Install the Claude Code app on GitHub
- Add your API key
- Automatically generate a pull request with the workflow files

The generated pull request adds two GitHub Actions to your repository. Once merged, you'll have the workflow files in your `.github/workflows` directory.

## Default GitHub Actions

The integration provides two main workflows:

### Mention Action

You can mention Claude in any issue or pull request using `@claude`. When mentioned, Claude will:

- Analyze the request and create a task plan
- Execute the task with full access to your codebase
- Respond with results directly in the issue or PR

### Pull Request Action

Whenever you create a pull request, Claude automatically:

- Reviews the proposed changes
- Analyzes the impact of modifications
- Posts a detailed report on the pull request

## Customizing the Workflows

After merging the initial pull request, you can customize the workflow files to fit your project's needs.

### Adding Project Setup

Before Claude runs, you can add steps to prepare your environment.
