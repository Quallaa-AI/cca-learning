---
module: 51
title: "Extended Thinking"
course: building-with-the-claude-api
topics: ["extended thinking", "thinking budget", "reasoning transparency", "redacted thinking"]
---
# Extended thinking

> Important Note: Extended Thinking is not compatible with some other features, notably message pre-filling and temperature. See the full list of restrictions here: https://docs.anthropic.com/en/docs/build-with-claude/extended-thinking#feature-compatibility

Extended thinking is Claude's advanced reasoning feature that gives the model time to work through complex problems before generating a final response. Think of it as Claude's "scratch paper" - you can see the reasoning process that leads to the answer, which helps with transparency and often results in better quality responses.

## How Extended Thinking Works

When extended thinking is enabled, Claude's response changes from a simple text block to a structured response containing two parts: the thinking process and the final answer.

The key benefits include:

- Better reasoning capabilities for complex tasks
- Increased accuracy on difficult problems
- Transparency into Claude's thought process

However, there are important trade-offs:

- Higher costs (you pay for thinking tokens)
- Increased latency (thinking takes time)
- More complex response handling in your code

## When to Use Extended Thinking

The decision is straightforward: use your prompt evaluations. Run your prompts without thinking first, and if the accuracy isn't meeting your requirements after you've already optimized your prompt, then consider enabling extended thinking. It's a tool for when standard prompting isn't quite getting you there.

## Response Structure and Security

Extended thinking responses include a special signature system for security. The signature is a cryptographic token that ensures you haven't modified the thinking text. This prevents developers from tampering with Claude's reasoning process, which could potentially lead the model in unsafe directions.

## Redacted Thinking

Sometimes you'll receive a redacted thinking block instead of readable reasoning text. This happens when Claude's thinking process gets flagged by internal safety systems. The redacted content contains the actual thinking in encrypted form, allowing you to pass the complete message back to Claude in future conversations without losing context.

## Implementation

To enable extended thinking in your code, you need to add two parameters to your chat function:

    def chat(
        messages,
        system=None,
        temperature=1.0,
        stop_sequences=[],
        tools=None,
        thinking=False,
        thinking_budget=1024
    ):

The thinking budget sets the maximum tokens Claude can use for reasoning. The minimum value is 1024 tokens, and your max_tokens parameter must be greater than your thinking budget.

Add the thinking configuration to your API parameters:

    if thinking:
        params["thinking"] = {
            "type": "enabled",
            "budget": thinking_budget
        }
