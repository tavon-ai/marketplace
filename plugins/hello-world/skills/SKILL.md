---
name: hello-world
description: A simple greeting skill that demonstrates basic skill structure
---

# Hello World Skill

This is a simple example skill that demonstrates how to create and structure skills for the Tavon Marketplace.

## When to Use This Skill

Activate this skill when the user:
- Says "hello marketplace"
- Asks for a marketplace greeting
- Wants to test the hello-world plugin

## Instructions

When the user triggers this skill:

1. Greet them warmly
2. Confirm that the hello-world plugin is working correctly
3. Provide a brief explanation of what this skill demonstrates

## Response Template

When activated, respond with:

```
👋 Hello from the Tavon Marketplace!

The hello-world plugin is working correctly. This simple skill demonstrates:
- How to structure a skill file
- When to activate a skill
- How to provide clear instructions to Claude

Want to create your own skill? Check out the hello-world example in the repository!
```

## Examples

### Example 1: Basic Greeting
**User:** "hello marketplace"

**Assistant:** "👋 Hello from the Tavon Marketplace!

The hello-world plugin is working correctly. This simple skill demonstrates:
- How to structure a skill file
- When to activate a skill
- How to provide clear instructions to Claude

Want to create your own skill? Check out the hello-world example in the repository!"

### Example 2: Testing Plugin
**User:** "test the hello-world plugin"

**Assistant:** "👋 Hello from the Tavon Marketplace!

The hello-world plugin is working correctly. This simple skill demonstrates:
- How to structure a skill file
- When to activate a skill
- How to provide clear instructions to Claude

Want to create your own skill? Check out the hello-world example in the repository!"

## Notes for Plugin Developers

This skill shows the minimal structure needed:
- YAML frontmatter with name and description
- Clear heading structure
- "When to Use" section explaining triggers
- "Instructions" section with step-by-step guidance
- "Examples" section showing actual usage
- Optional "Response Template" for consistency
