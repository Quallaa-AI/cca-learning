---
module: 52
title: "Image Support"
course: building-with-the-claude-api
topics: ["vision capabilities", "image analysis", "base64 encoding", "visual prompting"]
---
# Image support

Claude's vision capabilities let you include images in your messages and ask Claude to analyze them in countless ways. You can ask Claude to describe what's in an image, compare multiple images, count objects, or perform complex visual analysis tasks.

## Image Handling Basics

There are several important limitations to keep in mind when working with images:

- Up to 100 images across all messages in a single request
- Max size of 5MB per image
- When sending one image: max height/width of 8000px
- When sending multiple images: max height/width of 2000px
- Images can be included as base64 encoding or a URL to the image
- Each image counts as tokens based on its dimensions: tokens = (width px x height px) / 750

To send an image to Claude, you include an image block in your user message alongside text blocks:

    with open("image.png", "rb") as f:
        image_bytes = base64.standard_b64encode(f.read()).decode("utf-8")

    add_user_message(messages, [...])

## Message Flow

The conversation works just like text-only interactions. Your server sends a user message containing both image and text blocks to Claude, and Claude responds with a text block containing its analysis.

## Prompting Techniques

The key to getting good results with images is applying the same prompting engineering techniques you'd use with text. Simple prompts often lead to poor results. For example, asking "How many marbles are in this image?" might return an incorrect count.

You can dramatically improve Claude's accuracy by:

- Providing detailed guidelines and analysis steps
- Using one-shot or multi-shot examples
- Breaking down complex tasks into smaller steps

## Step-by-Step Analysis

Instead of a simple question, provide Claude with a methodology:

> Analyze this image of marbles and determine the exact count using this methodology:
> 1. Begin by identifying each unique marble one at a time. Assign each a number as you identify it.
> 2. Verify your result by counting with a different method. Start from the bottom-left corner and work row by row, from left to right.
>
> What is the exact, verified number of marbles in this image?

## One-Shot Examples

You can also improve accuracy by providing examples within your message. Include an image with a known count, state the correct answer, then ask about your target image. This gives Claude a reference point for the type of analysis you want.

## Real-World Example: Fire Risk Assessment

Here's a practical application: automating fire risk assessments for home insurance. Instead of sending inspectors to every property, insurance companies can use satellite imagery and Claude's analysis.

The system analyzes satellite images to identify:

- Dense, close-packed trees near the residence
- Difficult access routes for emergency services
- Branches overhanging the residence

Rather than a simple prompt like "provide a fire risk score," a well-structured prompt breaks down the analysis into specific steps:

1. **Residence identification:** Locate the primary residence on the property
2. **Tree overhang analysis:** Examine all trees near the primary residence and estimate roof coverage
3. **Fire risk assessment:** Evaluate wildfire vulnerability and proximity to roof openings
4. **Defensible space identification:** Assess the property's overall vegetative structure
5. **Fire risk rating:** Assign a rating from 1-4 based on the analysis

This detailed prompt guides Claude through a systematic analysis, resulting in much more accurate and useful assessments than a simple request would provide.

Remember: the same prompting techniques that work for text apply to images. Invest time in crafting detailed, structured prompts rather than relying on simple questions if you want reliable results.
