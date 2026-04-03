---
module: 24
title: "Prompt Engineering"
course: building-with-the-claude-api
topics: ["iterative improvement", "evaluation pipeline", "prompt refinement", "PromptEvaluator"]
---
# Prompt engineering

Prompt engineering is about taking a prompt you've written and improving it to get more reliable, higher-quality outputs. This process involves iterative refinement - starting with a basic prompt, evaluating its performance, then systematically applying engineering techniques to improve it.

## The Iterative Improvement Process

The approach follows a clear cycle that you can repeat until you achieve your desired results:

1. **Set a goal** - Define what you want your prompt to accomplish
2. **Write an initial prompt** - Create a basic first attempt
3. **Evaluate the prompt** - Test it against your criteria
4. **Apply prompt engineering techniques** - Use specific methods to improve performance
5. **Re-evaluate** - Verify that your changes actually improved the results

You repeat the last two steps until you're satisfied with the performance. Each iteration should show measurable improvement in your evaluation scores.

## Setting Up Your Evaluation Pipeline

To demonstrate this process, we'll work with a practical example: creating a prompt that generates one-day meal plans for athletes. The prompt needs to take into account an athlete's height, weight, goals, and dietary restrictions, then produce a comprehensive meal plan.

The evaluation setup uses a PromptEvaluator class that handles dataset generation and model grading. When creating your evaluator instance, you can control concurrency with the max_concurrent_tasks parameter:

    evaluator = PromptEvaluator(max_concurrent_tasks=5)

Start with a low concurrency value (like 3) to avoid rate limit errors. You can increase it if your API quota allows for faster processing.

## Generating Test Data

The evaluation system can automatically generate test cases based on your prompt requirements. You define what inputs your prompt needs:

    dataset = evaluator.generate_dataset(
        task_description="Write a compact, concise 1 day meal plan for a single athlete",
        prompt_inputs_spec={
            "height": "Athlete's height in cm",
            "weight": "Athlete's weight in kg",
            "goal": "Goal of the athlete",
            "restrictions": "Dietary restrictions of the athlete"
        }
    )
