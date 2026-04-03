---
module: 18
title: "Another useful hook"
course: claude-code-in-action
topics:
  - hook debugging
  - stdin inspection
  - TodoWrite tool
---

# Another useful hook

For example, here's a sample of some stdin input to a hook, where the hook is a PostToolUse that was watching for uses of the TodoWrite tool. For reference, that is the tool that Claude uses to keep track of to-do items.

Notice the provided command. It will write the input to this hook to the `post-log.json` file, which allows you to inspect exactly what would have been fed into your command. This makes it a lot easier for you to understand what data your command should inspect.
