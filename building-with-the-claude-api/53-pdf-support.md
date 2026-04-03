---
module: 53
title: "PDF Support"
course: building-with-the-claude-api
topics: ["PDF processing", "document analysis", "file encoding"]
---
# PDF support

Claude can read and analyze PDF files directly, making it a powerful tool for document processing. This capability works similarly to image processing, but with a few key differences in how you structure your code.

## Setting Up PDF Processing

To process a PDF file with Claude, you'll use nearly identical code to what you'd use for images. The main differences are in the file type specifications and variable names for clarity.

Here's how to modify your existing image processing code for PDFs:

    with open("earth.pdf", "rb") as f:
        file_bytes = base64.standard_b64encode(f.read()).decode("utf-8")

    messages = []

    add_user_message(messages, [...])
