---
module: 17
title: "A Typical Eval Workflow"
course: building-with-the-claude-api
topics: ["eval workflow", "prompt iteration", "test cases"]
---
# A typical eval workflow

A typical prompt evaluation workflow follows five key steps that help you systematically improve your prompts through objective measurement. While there are many different ways to assemble these workflows and various open source and paid tools available, understanding the core process helps you start small and scale up as needed.

## Step 1: Draft a Prompt

Start by writing an initial prompt that you want to improve. For this example, we'll use a simple prompt:

    prompt = f"""
    Please answer the user's question:
    ...
    """
