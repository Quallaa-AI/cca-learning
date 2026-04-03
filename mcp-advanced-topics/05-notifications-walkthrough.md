---
module: 5
title: "Notifications walkthrough"
course: mcp-advanced-topics
---
# Notifications walkthrough

Notifications walkthrough
Open in Claude
1. Tool function receives Context argument

Tool functions automatically receive 'Context' as their last argument. This object has methods for logging and reporting progress to the client.

2. Create logs and progress with context
3. Define callbacks on the client
4. Pass callbacks to appropriate functions
← Previous
Next →
FILES
📄
.gitignore
📄
client.py
📄
pyproject.toml
📄
README.md
📄
server.py
server.py
×
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
from mcp.server.fastmcp 
import FastMCP, Context
import asyncio
mcp = FastMCP(name="Demo 
Server")
@mcp.tool()
async def add(a: int, b: 
int, ctx: Context) -> int:
    await ctx.info
    ("Preparing to add...
    ")
    await ctx.
    report_progress(20, 
    100)
    await asyncio.sleep(2)
    await ctx.info("OK, 
    adding...")
    await ctx.
    report_progress(80, 
    100)
Downloads
notifications.zip
Previous - Log and progress notifications
Roots Next 
Tutorial Steps

Let's get a better sense of how to implement this feature by walking through a sample project.

Skip
Next
