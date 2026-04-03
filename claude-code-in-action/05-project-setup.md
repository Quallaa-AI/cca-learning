---
module: 5
title: "Project setup"
course: claude-code-in-action
topics:
  - project configuration
  - Node.js setup
  - Anthropic API key
  - sample project
---

# Project setup

Working with Claude Code is more interesting if you have a project to work with.

I've put together a small project to explore with Claude Code. It is the same UI generation app shown in a previous video. Note: you don't have to run this project. You can always follow along with the remainder of the course with your own code base if you wish!

## Setup

This project requires a small amount of setup:

- Ensure you have Node JS installed locally. Link to installation directions.
- Download the zip file called uigen.zip attached to this lecture and extract it
- In the project directory, run `npm run setup` to install dependencies and set up a local SQLite database
- Optional: this project uses Claude through the Anthropic API to generate UI components. If you want to fully test out the app, you will need to provide an API key to access the Anthropic API. This is optional. If no API key is provided, the app will still generate some static fake code. Here's how you can set the api key:
  - Get an Anthropic API key at https://console.anthropic.com/
  - Place your API key in the `.env` file.

Start the project by running `npm run dev`.
