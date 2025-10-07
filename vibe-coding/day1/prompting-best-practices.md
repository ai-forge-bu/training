# AI Prompting Best Practices

A guide to effectively communicate with AI code assistants like Google Gemini to get the best results.

## The Golden Rule
**Be specific, provide context, and iterate.**

AI assistants work best when they understand:
1. **What** you want to build
2. **Why** you need it
3. **How** it should work
4. **What** technology/constraints you have

---

## Good vs Bad Prompts

### ❌ Bad Prompt Examples

**Too vague:**
```
Create a website
```
*Problem: No context, no requirements, AI will make too many assumptions*

**Too short:**
```
Make it better
```
*Problem: AI doesn't know what "better" means to you*

**Assumes AI can see your screen:**
```
Fix this error
```
*Problem: AI can't see your error message unless you share it*

### ✅ Good Prompt Examples

**Specific with context:**
```
I want to create a simple personal portfolio website with:
- A homepage with my photo and bio
- A projects section showing 3 projects with images and descriptions
- A contact form with name, email, and message fields
- Clean, modern design
- Works on mobile phones and computers

I'm a beginner. What technology should I use to build this, and can you help me get started?
```

**Includes error details:**
```
I'm getting this error message:
"Cannot find module 'react-router-dom'"

I'm trying to [describe what you were doing].
Here's my code: [paste relevant code]

How do I fix this?
```

**Iterative improvement:**
```
Can you improve the contact form you just created by:
1. Checking if the email address is valid before submitting
2. Showing a success message after submission
3. Making it look more professional
```

---

## Effective Prompting Strategies

### 1. Ask AI to Recommend Technology (You Don't Need to Know!)

**Important:** You don't need to decide what technology to use. Let the AI recommend it!

**Good starting prompt:**
```
I want to build a tool that [describe your solution and what it should do].

I'm not a developer, so I need your help choosing the right technology.

Requirements:
- I'm a complete beginner
- Needs to work on both computers and mobile phones
- Should be deployable to Netlify or Vercel
- Doesn't need a complex database (can save data in the browser)

What technology should I use? Please explain in simple terms why you're recommending it.
```

**The AI will recommend appropriate technologies and explain them in beginner-friendly terms.**

### 2. Focus on WHAT, Not HOW
Describe what you want to achieve, not how to build it. Let the AI figure out the "how."

**Example:**
```
I want to build a tool that helps me track my daily water intake.
Users should be able to:
- Log glasses of water consumed
- See their daily goal and progress
- View history for the past 7 days

I'm a beginner - what's the simplest way to build this?
```

### 3. Share Relevant Code
When asking for help with existing code, share it!

**Example:**
```
I have this function but it's not working correctly:

[paste code]

When I call it with input X, I expect Y but I'm getting Z.
Can you help me fix it?
```

### 4. Ask for Explanations
Don't just get code - understand it!

**Example:**
```
Can you create a sorting function for my product list?
Please also explain:
1. How the sorting algorithm works
2. Why you chose this approach
3. What the time complexity is
```

### 5. Break Down Complex Tasks
Don't try to build everything at once.

**Instead of:**
```
Build a complete e-commerce website
```

**Do this:**
```
Step 1: Create a product listing page with mock data
Step 2: Add a shopping cart that stores items in localStorage
Step 3: Add a checkout form
[etc.]
```

### 6. Iterate and Refine
Build progressively - start simple, then enhance.

**Example:**
```
Prompt 1: "Create a basic todo list with add/delete functionality"
Prompt 2: "Add the ability to mark todos as complete"
Prompt 3: "Add categories/tags to todos"
Prompt 4: "Make it persist using localStorage"
```

---

## Dos and Don'ts

### ✅ DO

- **Be specific** about what you want
- **Provide examples** of desired output
- **Share error messages** completely (full stack trace)
- **Mention your skill level** ("I'm new to JavaScript")
- **Ask for explanations** when you don't understand
- **Request best practices** ("What's the recommended way to...")
- **Specify constraints** (browser support, file size, performance)
- **Test the code** AI gives you - it can make mistakes!

### ❌ DON'T

- Don't assume AI knows your project structure
- Don't paste code without context
- Don't accept code you don't understand
- Don't skip testing AI-generated code
- Don't ask for illegal/unethical functionality
- Don't copy sensitive data (API keys, passwords) into prompts
- Don't expect AI to be perfect - it makes mistakes

---

## Common Prompting Patterns

### Pattern 1: The Feature Request
```
I need to add [FEATURE] to my [PROJECT TYPE].

Requirements:
- [Requirement 1]
- [Requirement 2]
- [Requirement 3]

Technical constraints:
- [Constraint 1]
- [Constraint 2]

Please provide the code with explanations.
```

### Pattern 2: The Debug Request
```
I'm experiencing [PROBLEM] in my [PROJECT].

What I expect: [EXPECTED BEHAVIOR]
What's happening: [ACTUAL BEHAVIOR]

Error message:
```
[PASTE ERROR]
```

Relevant code:
```
[PASTE CODE]
```

How can I fix this?
```

### Pattern 3: The Learning Request
```
I want to learn how to [SKILL/CONCEPT].

Can you:
1. Explain the concept simply
2. Show me a practical example
3. Point out common mistakes to avoid
4. Give me a small exercise to practice
```

### Pattern 4: The Review Request
```
Can you review this code and suggest improvements?

Focus on:
- Performance
- Security
- Best practices
- Code readability

Here's the code:
[PASTE CODE]
```

---

## Tips for "Vibe Coding" Success

### Start with spec.md
Always write your specification first! This becomes your master prompt.

Your spec should include:
- Problem you're solving
- User stories ("As a user, I want to...")
- Technical requirements
- Success criteria

### Use Your spec.md as Context
When prompting AI, reference your spec:

```
Based on my spec.md [paste or reference relevant parts],
I want to start by building the [SPECIFIC FEATURE].
```

### Keep Prompts in Context
Build on previous responses:

```
Good: "Now add validation to the form you just created"
Bad: "Add form validation" (AI needs context)
```

### Save Good Prompts
Keep a notes file with prompts that worked well. Reuse and adapt them!

### When AI Gets It Wrong
Don't just regenerate - guide it:

```
That's close, but instead of using [X], can you use [Y]?
Also, the function should handle [EDGE CASE].
```

---

## Example: Full Conversation Flow

**You:**
```
I want to build a simple expense tracker. Users should be able to:
- Add expenses with amount, category, and date
- View list of all expenses
- See total expenses
- Delete expenses

Tech: HTML, CSS, JavaScript (no frameworks)
Data: Store in localStorage
Design: Simple, clean, mobile-friendly
```

**AI:** [Provides code]

**You:**
```
Great! Now can you:
1. Add a filter to show expenses by category
2. Display expenses grouped by month
3. Add validation so amount must be a positive number
```

**AI:** [Provides updated code]

**You:**
```
The month grouping isn't working correctly. When I add an expense
from January and one from February, they both show under January.

Here's the relevant code:
[paste code]

Can you fix this?
```

**AI:** [Fixes the bug]

**You:**
```
Perfect! Can you explain how the month grouping logic works?
I want to understand it so I can maintain this code.
```

---

## Practice Exercise

Try improving this bad prompt:

**Bad:**
```
make a calculator
```

**Your turn:** Write a better version using what you learned!

<details>
<summary>See example good prompt</summary>

**Good:**
```
Create a simple calculator web app with:

Features:
- Basic operations: +, -, *, /
- Clear button to reset
- Display showing current number/result
- Keyboard input support

Technical requirements:
- HTML, CSS, JavaScript (vanilla, no frameworks)
- Clean, modern UI
- Works on mobile and desktop
- Should handle decimal numbers
- Should prevent division by zero

Please provide:
1. Complete code (HTML, CSS, JS)
2. Brief explanation of how the calculation logic works
```
</details>

---

## Remember

**AI is your coding partner, not a magic wand.**

- You're still the developer - review and understand all code
- AI helps you go faster, but you decide the direction
- When stuck, re-read your spec.md and adjust your prompts
- Don't hesitate to ask for clarification or alternatives

**Good prompting is a skill - you'll get better with practice!**

---

## Quick Reference Card

**The Perfect Prompt Template:**
```
Context: [What are you building? What's the current state?]
Goal: [What do you want to achieve?]
Requirements: [Specific features/behaviors needed]
Constraints: [Tech stack, limitations, preferences]
Question: [Your specific ask]
```

Print this out or keep it handy while coding!
