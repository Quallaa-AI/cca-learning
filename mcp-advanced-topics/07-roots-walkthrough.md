---
module: 7
title: "Roots walkthrough"
course: mcp-advanced-topics
---
# Roots walkthrough

Roots walkthrough
Open in Claude
1. Defining roots

Ideally, a user will dictate which files/folders can be accessed by the MCP server.

This program is set up to accept a list of CLI arguments, which are interpretted as paths that the user wants to allow access to.

That list of paths is provided to the MCPClient down on lines 42.

2. Creating root objects
3. Roots callback
4. Using the roots
5. Accessing the roots
6. Authorizing access
7. Authorizing access
← Previous
Next →
FILES
📂
core
📄
__init__.py
📄
chat.py
📄
claude.py
📄
cli_chat.py
📄
cli.py
📄
tools.py
📄
utils.py
📄
video_converter.py
📄
.env.example
📄
.gitignore
📄
main.py
📄
mcp_client.py
📄
mcp_server.py
📄
pyproject.toml
📄
README.md
main.py
×
23
24
25
26
27
28
29
30
31
32
33
34
35
36
    cannot be empty. 
    Update .env"
)
async def main():
    claude_service = 
    Claude
    (model=claude_model)
    # Get root 
    directories from 
    command line arguments
    root_paths = sys.argv
    [1:]
    if not root_paths:
        print("Usage: uv 
        run main.py 
        <root1> 
        [root2] ...")
        print("Example: 
        uv run main.py /
        path/to/videos /
        another/path")
        sys.exit(1)
    clients = {}
Downloads
roots.zip
Previous - Roots
Survey Next 
Tutorial Steps

Let's get a better sense of how to implement this feature by walking through a sample project.

Skip
Next
