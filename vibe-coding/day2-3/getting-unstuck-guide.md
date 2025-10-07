# Getting Unstuck Guide

A practical guide for when you're blocked during independent coding (Day 2-3).

---

## 🛑 You're Stuck. Now What?

**First, take a breath.** Getting stuck is normal - it happens to professional developers constantly. Here's your step-by-step guide to get moving again.

---

## The 5-Minute Self-Help Protocol

Before asking for help, try this (5 minutes max):

### 1. Read the Error Message (1 minute)
- Don't panic - read it carefully
- Error messages usually tell you what's wrong
- Note the line number if provided
- Copy the full error message

### 2. Check Your Code (2 minutes)
Common mistakes to look for:
- ✅ Spelling errors in variable/function names
- ✅ Missing closing brackets `}`, `)`, `]`
- ✅ Missing semicolons (in some languages)
- ✅ Quotes not closed properly `"` or `'`
- ✅ Case sensitivity (fileName vs filename)

### 3. Ask AI for Help (2 minutes)
Use this prompt template:
```
I'm getting this error:
[paste full error message]

Here's my code:
[paste relevant code]

I'm trying to [what you want to achieve].
What's wrong and how do I fix it?
```

---

## When AI Isn't Helping

AI gave you code but it's not working?

### Strategy 1: Test in Isolation
**Problem:** Too much code, can't find the bug

**Solution:**
1. Create a new simple test file
2. Test just the problematic function alone
3. Use simple inputs
4. See if it works in isolation

**Example:**
```javascript
// Instead of testing in your full app, create test.js:
function problemFunction(input) {
  // paste the function here
}

// Test with simple data
console.log(problemFunction("test"));
```

### Strategy 2: Break Down the Problem
**Problem:** Feature is too complex, overwhelming

**Solution:**
Ask AI to build it step-by-step:

```
Instead of doing everything at once, let's break this down.

Step 1: First, just create the basic HTML form
(Don't worry about validation or saving data yet)
```

Then after Step 1 works:
```
Good! Now add validation to the form we just created.
```

### Strategy 3: Go Back to Basics
**Problem:** Code is getting messy and confusing

**Solution:**
Sometimes it's better to restart cleanly:
1. Create a new file
2. Start with the simplest version that works
3. Add features one at a time
4. Test after each addition

**Remember:** Working simple code > Broken complex code

---

## Common Problems & Quick Fixes

### Problem: "Nothing happens" when I click/run
**Quick checks:**
- ✅ Is JavaScript file linked in HTML? `<script src="app.js"></script>`
- ✅ Is the script tag at the end of body? (Before `</body>`)
- ✅ Are there errors in the console? (F12 > Console tab)
- ✅ Is the file saved? (Check for dot in tab name)

**Fix:**
Open browser console (F12) and look for error messages.

---

### Problem: Changes don't show up
**Quick checks:**
- ✅ Did you save the file? (Ctrl/Cmd + S)
- ✅ Did you refresh the browser? (Ctrl/Cmd + R)
- ✅ Is browser caching old version? (Hard refresh: Ctrl/Cmd + Shift + R)
- ✅ Are you editing the right file?

**Fix:**
Save, hard refresh (Ctrl/Cmd + Shift + R), check file path.

---

### Problem: "X is not defined"
**Meaning:** You're using a variable/function that doesn't exist

**Common causes:**
- Typo in the name
- Variable declared in wrong scope
- Script loaded in wrong order
- Forgot to import/include a library

**Fix:**
```javascript
// Make sure variable is declared before use:
let myVariable = "hello";  // declared first
console.log(myVariable);    // used second
```

---

### Problem: "Cannot read property of undefined/null"
**Meaning:** You're trying to access a property of something that doesn't exist

**Example:**
```javascript
let user = null;
console.log(user.name);  // Error! user is null
```

**Fix:**
Check if thing exists first:
```javascript
if (user) {
  console.log(user.name);
}
```

---

### Problem: Styling not working
**Quick checks:**
- ✅ CSS file linked in HTML? `<link rel="stylesheet" href="style.css">`
- ✅ Correct class/id names? (case-sensitive)
- ✅ Specificity issues? (another style overriding)
- ✅ Typos in CSS property names?

**Debug tip:**
Right-click element > Inspect > See what styles are applied

---

### Problem: Data not saving
**If using localStorage:**
```javascript
// Save
localStorage.setItem('key', JSON.stringify(data));

// Load
const data = JSON.parse(localStorage.getItem('key'));
```

**Common mistakes:**
- Forgot `JSON.stringify` when saving
- Forgot `JSON.parse` when loading
- Saving but not loading on page load

---

## When to Ask Your PIC for Help

**Ask for help if:**
- ⏰ You've been stuck for **more than 15 minutes**
- 🔄 You've tried the same fix 3 times and it still doesn't work
- ❓ You don't understand the error message at all
- 🤔 AI's suggestions aren't making sense
- 📉 You're feeling frustrated or overwhelmed

**Don't wait until you're completely blocked!**

---

## How to Ask for Help Effectively

### ❌ Less Effective
"My code doesn't work, can you help?"

### ✅ More Effective
"I'm trying to add a delete button to my todo list. When I click it, I get this error: [error message]. I've tried [what you tried]. Here's my code: [code]. Can you help me figure out what's wrong?"

### The Perfect Help Request Template

```
**What I'm trying to do:**
[Brief description]

**What's happening instead:**
[Actual behavior / error message]

**What I've tried:**
1. [Thing 1]
2. [Thing 2]

**Code:**
[Relevant code snippet]

**Question:**
[Specific question]
```

---

## Debugging Tools

### Browser Console (F12)
Your best friend for debugging JavaScript.

**How to use:**
1. Press F12 in browser
2. Go to "Console" tab
3. Look for red error messages
4. Click the error to see which line of code

**Pro tip:** Add `console.log()` to see what's happening:
```javascript
console.log("Got here!");
console.log("Value of x:", x);
```

### VS Code Debugging Features
- **Syntax highlighting** - Wrong color? Probably a typo
- **Bracket matching** - Click a bracket to see its pair
- **Error squiggles** - Red underlines show problems
- **Problems panel** - View > Problems to see all issues

---

## Mindset Tips

### It's Not Just You
- Professional developers get stuck all the time
- Getting unstuck is a learnable skill
- Every problem you solve makes you better

### Take Breaks
If stuck for 20+ minutes:
1. Stand up
2. Walk around for 5 minutes
3. Come back with fresh eyes

Often you'll see the problem immediately.

### Progress Over Perfection
**Better to have:**
- ✅ A working simple version
- ❌ A broken complex version

You can always improve working code.

### Celebrate Small Wins
Got something working? Great!
- Save your progress
- Test it thoroughly
- Then move to the next feature

---

## Emergency Contact

**Your PIC is here to help!**

**Group 1:** Nanda
**Group 2:** Nathania
**Group 3:** Desi

**When to reach out:**
- Stuck for 15+ minutes
- Need clarification on approach
- Want code review
- Feeling overwhelmed

**How to reach out:**
- Slack message (preferred)
- In person if in office
- Don't suffer in silence!

---

## Quick Reference: Debugging Checklist

```
[ ] Read the error message carefully
[ ] Check browser console (F12)
[ ] Is file saved?
[ ] Is browser refreshed? (Try hard refresh)
[ ] Are there typos in variable/function names?
[ ] Are brackets/quotes closed?
[ ] Is JavaScript file linked in HTML?
[ ] Asked AI with full error message and code?
[ ] Tried testing in isolation?
[ ] Checked this guide?
[ ] Been stuck 15+ minutes? → Ask PIC!
```

---

## Remember

**Every developer gets stuck. The best developers know how to get unstuck quickly.**

You're learning a valuable skill - debugging is a huge part of programming. Be patient with yourself and don't hesitate to ask for help!

**You've got this! 💪**
