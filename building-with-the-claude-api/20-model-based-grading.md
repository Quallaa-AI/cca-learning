---
module: 20
title: "Model Based Grading"
course: building-with-the-claude-api
topics: ["model graders", "code graders", "evaluation criteria", "grading approaches"]
---
# Model based grading

When building prompt evaluation workflows, grading systems provide objective signals about output quality. A grader takes model output and returns some kind of measurable feedback - typically a number between 1 and 10, where 10 represents high quality and 1 represents poor quality.

## Types of Graders

There are three main approaches to grading model outputs:

- **Code graders** - Programmatically evaluate outputs using custom logic
- **Model graders** - Use another AI model to assess the quality
- **Human graders** - Have people manually review and score outputs

## Code Graders

Code graders let you implement any programmatic check you can imagine. Common uses include:

- Checking output length
- Verifying output does/doesn't have certain words
- Syntax validation for JSON, Python, or regex
- Readability scores

The only requirement is that your code returns some usable signal - usually a number between 1 and 10.

## Model Graders

Model graders are useful for evaluating subjective qualities like:

- General response quality
- Comprehensiveness
- Depth
- Conciseness
- Relevance

## Defining Evaluation Criteria

Before implementing any grader, you need clear evaluation criteria. For a code generation prompt, you might focus on:

- **Format** - Should return only Python, JSON, or Regex without explanation
- **Valid Syntax** - Produced code should have valid syntax
- **Task Following** - Response should directly address the user's task with accurate code
