---
module: 37
title: "Multi-Turn Conversations with Tools"
course: building-with-the-claude-api
topics: ["multi-turn tools", "conversation loops", "sequential tool calls"]
---
# Multi-turn conversations with tools

When building applications with multiple tools, you need to handle scenarios where Claude might need to call several tools in sequence to answer a single user question. For example, if a user asks "What day is 103 days from today?", Claude needs to first get the current date, then add 103 days to it.

This creates a multi-turn conversation pattern where Claude makes multiple tool requests before providing a final answer. Your application needs to handle this automatically.

## The Multi-Turn Tool Pattern

Here's what happens behind the scenes when Claude needs multiple tools:

1. User asks: "What day is 103 days from today?"
2. Claude responds with a tool use block requesting get_current_datetime
3. Your server calls the function and returns the result
4. Claude realizes it needs more information and requests add_duration_to_datetime
5. Your server calls that function and returns the result
6. Claude now has enough information to provide the final answer

## Building a Conversation Loop

To handle this pattern, you need a conversation loop that continues until Claude stops requesting tools:

    def run_conversation(messages):
        while True:
            response = chat(messages)
            add_user_message(messages, response)
            ...

## Refactoring Helper Functions

Before implementing the conversation loop, you need to update your helper functions to handle multiple message blocks properly.

### Updating Message Handlers

Your add_user_message and add_assistant_message functions currently assume you're always working with plain text. Update them to handle full message objects:

    from anthropic.types import Message

    def add_user_message(messages, message):
        user_message = {
            "role": "user",
            "content": message.content if isinstance(message, Message) else message
        }
        ...
        messages.append(user_message)

This allows you to pass in either a string, a list of blocks, or a complete message object.

### Updating the Chat Function

Modify your chat function to accept a list of tools and return the full message instead of just text:

    def chat(messages, system=None, temperature=1.0, stop_sequences=[], tools=None):
        params = {
            "model": model,
            "max_tokens": 1000,
            "messages": messages,
            "temperature": temperature,
            "stop_sequences": stop_sequences,
            ...
        }
