---
module: 80
title: "Agents and Tools"
course: building-with-the-claude-api
topics: ["agent design", "abstract tools", "tool composition", "adaptive behavior"]
---
# Agents and tools

Agents represent a shift from the structured workflows we've been working with. While workflows are perfect when you know the exact steps needed to complete a task, agents shine when you're not sure what those steps should be. Instead of defining a rigid sequence, you give Claude a goal and a set of tools, then let it figure out how to combine those tools to achieve the objective.

## How Tools Make the Agent

The real power of agents lies in their ability to combine simple tools in unexpected ways. Consider a basic set of datetime tools:

- **get_current_datetime** - Gets the current date and time
- **add_duration_to_datetime** - Adds time to a given date
- **set_reminder** - Creates a reminder for a specific time

These tools seem simple individually, but Claude can chain them together to handle surprisingly complex requests:

For "What's the time?", Claude simply calls get_current_datetime. But for "What day of the week is it in 11 days?", it chains get_current_datetime followed by add_duration_to_datetime. For setting a gym reminder next Wednesday, it might use all three tools in sequence.

Claude can even recognize when it needs more information. If you ask "When does my 90-day warranty expire?", it knows to ask when you purchased the item before calculating the expiration date.

## Tools Should Be Abstract

The key insight for building effective agents is providing reasonably abstract tools rather than hyper-specialized ones. Claude Code demonstrates this principle perfectly.
