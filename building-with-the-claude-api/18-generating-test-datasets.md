---
module: 18
title: "Generating Test Datasets"
course: building-with-the-claude-api
topics: ["test dataset generation", "evaluation setup", "prompt versioning"]
---
# Generating test datasets

Building a custom prompt evaluation workflow starts with creating a solid prompt and then generating test data to see how well it performs. Let's walk through setting up an evaluation system for a prompt that helps users write AWS-specific code.

## Setting Up the Goal

Our prompt needs to assist users in writing three specific types of output for AWS use cases:

- Python code
- JSON configuration files
- Regular expressions

The key requirement is that when a user requests help with a task, we return clean output in one of these formats without any extra explanations, headers, or footers.

Here's our starting prompt (version 1):

    prompt = f"""
    Please provide a solution to the following task:
    ...
    """
