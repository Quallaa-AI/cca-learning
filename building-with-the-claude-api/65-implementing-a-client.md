---
module: 65
title: "Implementing a Client"
course: building-with-the-claude-api
topics: ["MCP client implementation", "client session", "list_tools", "call_tool"]
---
# Implementing a client

Now that we have our MCP server working, it's time to build the client side. The client is what allows our application to communicate with the MCP server and access its functionality.

## Understanding the Client Architecture

In most real-world projects, you'll either implement an MCP client OR an MCP server - not both. We're building both in this project just so you can see how they work together.

The MCP client consists of two main components:

- **MCP Client** - A custom class we create to make using the session easier
- **Client Session** - The actual connection to the server (part of the MCP Python SDK)

The client session requires proper resource cleanup when we're done with it. That's why we wrap it in our custom MCP Client class - to handle all that cleanup automatically.

## How the Client Fits Into Our Application

Remember our application flow? Our CLI code needs to do two main things with the MCP server:

1. Get a list of available tools to send to Claude
2. Execute tools when Claude requests them

The MCP client provides these capabilities through simple method calls that our application code can use.

## Implementing the Core Methods

We need to implement two key methods in our client: list_tools() and call_tool().

### List Tools Method

This method gets all available tools from the server. It's straightforward - we access our session (the connection to the server), call the built-in list_tools() function, and return the tools from the result.

### Call Tool Method

This method executes a specific tool on the server. We pass the tool name and input parameters (provided by Claude) to the server and return the result.

## Testing the Client

To test our implementation, we can run the client directly. The file includes a testing harness that connects to our MCP server and calls our methods.
