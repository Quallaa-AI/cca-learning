---
module: 3
title: "Sampling walkthrough"
course: mcp-advanced-topics
---
# Sampling walkthrough

Sampling walkthrough
Open in Claude
1. Initiating sampling

On the server, during a tool call, run the create_message() method, passing in some messages that you wish to send to a language model.

2. Sampling callbacks
3. Message formats
4. Returning generated text
5. Connecting the callback
6. Getting the result
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
17
@mcp.tool()
async def summarize
(text_to_summarize: str, 
ctx: Context):
    prompt = f"""
        Please summarize 
        the following 
        text:
        {text_to_summarize
        }
    """
    result = await ctx.
    session.create_message
    (
        messages=[
            SamplingMessag
            e(
                role="user
                ", 
                content=Te
                xtContent
                (type="tex
                t", 
                text=promp
                t)
Downloads
sampling.zip
Previous - Sampling
Log and progress notifications Next 
Tutorial Steps

Let's get a better sense of how to implement this feature by walking through a sample project.

Skip
Next
