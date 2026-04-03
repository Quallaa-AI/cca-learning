---
module: 33
title: "Tool Functions"
course: building-with-the-claude-api
topics: ["tool functions", "input validation", "error handling", "datetime tools"]
---
# Tool functions

When building AI applications with Claude, you'll often need to give it access to real-time information or the ability to perform actions. This is where tool functions come in - they're Python functions that Claude can call when it needs additional data to help users.

## What Are Tool Functions?

A tool function is a plain Python function that gets executed automatically when Claude decides it needs extra information to help a user. For example, if someone asks "What time is it?", Claude would call your date/time tool to get the current time.

Here's an example of a weather tool function. Notice how it validates inputs and provides clear error messages - these are important best practices.

## Best Practices for Tool Functions

When writing tool functions, follow these guidelines:

- **Use descriptive names:** Both your function name and parameter names should clearly indicate their purpose
- **Validate inputs:** Check that required parameters aren't empty or invalid, and raise errors when they are
- **Provide meaningful error messages:** Claude can see error messages and might retry the function call with corrected parameters

The validation is particularly important because Claude learns from errors. If you raise a clear error like "Location cannot be empty", Claude might try calling the function again with a proper location value.

## Building Your First Tool Function

Let's create a function to get the current date and time. This function will accept a date format parameter so Claude can request the time in different formats:

    def get_current_datetime(date_format="%Y-%m-%d %H:%M:%S"):
        if not date_format:
            raise ValueError("date_format cannot be empty")
        ...

This function uses Python's datetime module to get the current time and format it according to the provided format string. The default format gives us year-month-day hour:minute:second.

You can test it with different formats.
