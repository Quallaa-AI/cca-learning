---
module: 38
title: "Implementing Multiple Turns"
course: building-with-the-claude-api
topics: ["stop_reason", "conversation loop", "run_tools", "error handling"]
---
# Implementing multiple turns

Building a conversation system with tools requires implementing a loop that keeps calling Claude until it stops requesting tool usage. When Claude no longer asks for tools, that signals it has a final response ready for the user.

## Detecting Tool Requests

The key to knowing whether Claude wants to use a tool lies in the stop_reason field of the response message. When Claude decides it needs to call a tool, this field gets set to "tool_use". This gives us a clean way to check if we need to continue the conversation loop:

    if response.stop_reason != "tool_use":
        break  # Claude is done, no more tools needed

## The Conversation Loop

The main conversation function follows a simple pattern:

    def run_conversation(messages):
        while True:
            response = chat(messages, tools=[get_current_datetime_schema])
            add_assistant_message(messages, response)
            print(text_from_message(response))

            if response.stop_reason != "tool_use":
                break

            tool_results = run_tools(response)
            add_user_message(messages, tool_results)

This loop continues until Claude provides a final answer without requesting any tools.

## Handling Multiple Tool Calls

Claude can request multiple tools in a single response. The message content contains a list of blocks, and we need to process each tool use block separately:

The run_tools function handles this by filtering for tool use blocks and processing each one:

    def run_tools(message):
        tool_requests = [
            block for block in message.content if block.type == "tool_use"
        ]
        tool_result_blocks = []

        for tool_request in tool_requests:
            ...

## Tool Result Blocks

Each tool use block must be answered with a corresponding tool result block. The connection between them is maintained through matching IDs:

    tool_result_block = {
        "type": "tool_result",
        "tool_use_id": tool_request.id,
        "content": json.dumps(tool_output),
        "is_error": False
    }

## Error Handling

Robust tool execution requires handling potential errors. When a tool fails, we still need to provide a result block to Claude.
