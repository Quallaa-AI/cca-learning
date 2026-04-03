---
module: 40
title: "Fine Grained Tool Calling"
course: building-with-the-claude-api
topics: ["tool streaming", "InputJsonEvent", "partial JSON", "real-time tool arguments"]
---
# Fine grained tool calling

When you combine tool use with streaming in Claude, you get real-time updates as the AI generates tool arguments. This creates a more responsive user experience, but there are some important details to understand about how it works behind the scenes.

## Basic Tool Streaming

With streaming enabled, Claude sends back different types of events as it processes your request. You're already familiar with events like ContentBlockDelta for regular text generation. For tool use, you'll also need to handle a new event type called InputJsonEvent.

Each InputJsonEvent contains two key properties:

- **partial_json** - A chunk of JSON representing part of the tool arguments
- **snapshot** - The cumulative JSON built up from all chunks received so far

Here's how you handle these events in your streaming pipeline:

    for chunk in stream:
        if chunk.type == "input_json":
            ...
