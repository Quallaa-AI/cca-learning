---
module: 46
title: "Text Embeddings"
course: building-with-the-claude-api
topics: ["text embeddings", "semantic search", "VoyageAI", "numerical representations"]
---
# Text embeddings

After breaking a document into chunks, the next step in a RAG pipeline is finding which chunks are most relevant to a user's question. This is essentially a search problem - you need to look through all your text chunks and identify the ones that relate to what the user is asking about.

## Semantic Search

The most common approach for finding relevant chunks is semantic search. Unlike keyword-based search that looks for exact word matches, semantic search uses text embeddings to understand the meaning and context of both the user's question and each text chunk.

## Text Embeddings

A text embedding is a numerical representation of the meaning contained in some text. Think of it as converting words and sentences into a format that computers can work with mathematically.

Here's how the process works:

1. You feed text into an embedding model
2. The model outputs a long list of numbers (the embedding)
3. Each number ranges from -1 to +1
4. These numbers represent different qualities or features of the input text

## Understanding the Numbers

Each number in an embedding is essentially a "score" for some quality of the input text. However, here's the important caveat: we don't know precisely what each number represents.

While it's helpful to imagine that one number might represent "how happy the text is" or "how much the text talks about oceans," these are just conceptual examples. The actual meaning of each dimension is learned by the model during training and isn't directly interpretable by humans.

## VoyageAI for Embeddings

Since Anthropic doesn't currently provide embedding generation, the recommended provider is VoyageAI. You'll need to:

1. Sign up for a separate VoyageAI account
2. Get an API key (free to get started)
3. Add the key to your environment variables

In your .env file, add:

    VOYAGE_API_KEY="your_key_here"

## Implementation

First, install the VoyageAI library:

    %pip install voyageai

Then set up the client and create a function to generate embeddings:

    from dotenv import load_dotenv
    ...

When you run this function on a text chunk, you'll get back a list of floating-point numbers representing the embedding. The process is quick and straightforward - the real challenge is understanding how to use these embeddings effectively in your RAG pipeline for finding the most relevant content.

The next step is learning how to compare embeddings to determine which chunks are most similar to a user's question, which forms the core of the semantic search process.
