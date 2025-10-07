# When to Ask Your PIC for Help

Guidelines on when to reach out vs. when to try solving it yourself.

---

## 🎯 The Golden Rule

**Try for 15 minutes. Then ask.**

- Stuck for 15+ minutes? → Time to ask
- Found it yourself in 10 minutes? → Great!
- Solved it in 5 minutes? → Awesome!

**Don't wait until you're completely stuck or frustrated.**

---

## ✅ DO Ask Your PIC When...

### Technical Blockers
- ❓ Error message you don't understand after checking troubleshooting guide
- ❓ Tried AI's suggestions 3+ times and still not working
- ❓ Not sure which technology/approach to use
- ❓ Need help understanding a concept AI explained

### Project Direction
- 🧭 Not sure if your approach is correct
- 🧭 Wondering if you should simplify your project scope
- 🧭 Need feedback on your progress
- 🧭 Want a code review before moving forward

### Best Practices
- 📚 Want to know the "right way" to do something
- 📚 Concerned about security or performance
- 📚 Need advice on organizing your code
- 📚 Unsure if your solution is deployable

### Time Management
- ⏰ Worried you're behind schedule
- ⏰ Not sure what to prioritize
- ⏰ Need help breaking down a complex feature
- ⏰ Feeling overwhelmed with scope

### Tooling Issues
- 🔧 VS Code or Gemini not working correctly
- 🔧 Git errors (if you're trying version control)
- 🔧 Environment setup problems
- 🔧 Local server not starting

---

## 🚫 DON'T Ask Your PIC When...

### First, Try These Instead

**Before asking about errors:**
- ✋ Haven't read the full error message
- ✋ Haven't checked browser console (F12)
- ✋ Haven't saved file and refreshed browser
- ✋ Haven't tried asking AI with the full error

**Before asking about approach:**
- ✋ Haven't looked at similar examples in common-patterns.md
- ✋ Haven't tried the simplest solution first
- ✋ Haven't asked AI to explain the concept

**Before asking for code help:**
- ✋ Haven't tested code in isolation
- ✋ Haven't checked for typos
- ✋ Haven't tried console.log debugging

---

## 🤔 How to Ask Effectively

### ❌ Less Helpful Requests

"Can you look at my code?"
- Too vague, PIC doesn't know what to focus on

"It's not working"
- What's "it"? What should it do? What's happening instead?

"I need help"
- With what specifically?

### ✅ Better Requests

**Good question format:**
```
"I'm trying to [goal].

Currently, when I [action], I expect [expected result],
but instead [actual result happens].

I've tried:
1. [Thing 1]
2. [Thing 2]

Here's my code: [link or snippet]

Can you help me understand what's wrong?"
```

**Example:**
```
"I'm trying to save my todo list to localStorage.

Currently, when I refresh the page, all my todos disappear.
I expect them to persist.

I've tried:
1. Adding localStorage.setItem when adding new todos
2. Using JSON.stringify as AI suggested
3. Checking if data is actually in localStorage (it is!)

Here's my save function: [code snippet]

Can you help me figure out why they're not loading back?"
```

---

## 📞 How to Reach Your PIC

### Communication Methods (in order of preference)

1. **Lark message** - Best for async questions
   - PIC can respond when available
   - You can continue working while waiting
   - Use for: Questions, code review requests, general guidance

2. **In-person (if in office)** - Good for complex issues
   - Best for debugging sessions
   - When you need to screen share
   - Use for: Deep technical issues, pair programming

3. **Video call** - If remote
   - Can share screen
   - Similar to in-person
   - Use for: Complex troubleshooting

### Response Time Expectations

**Normal hours (during work day):**
- Lark: ~30 minutes
- In-person: Usually available

**After hours / Weekend:**
- PICs are available but may take longer
- For emergencies only

**If urgent:**
- Mention "urgent" or "blocked"
- Try other PIC if yours is unavailable

---

## 🔄 Self-Help Workflow

Follow this before asking:

```
1. Encounter problem
   ↓
2. Read error / understand what's wrong (2 min)
   ↓
3. Check troubleshooting guide (2 min)
   ↓
4. Try obvious fixes (save, refresh, typos) (2 min)
   ↓
5. Ask AI with full context (5 min)
   ↓
6. Try AI's suggestion (5 min)
   ↓
7. Still stuck after 15 min total?
   ↓
8. Ask PIC with full context
```

---

## 📋 Before Asking Checklist

```
[ ] I've been stuck for 15+ minutes
[ ] I've read the error message carefully
[ ] I've checked browser console
[ ] I've saved files and refreshed browser
[ ] I've checked for obvious typos
[ ] I've asked AI with full error/code
[ ] I've tried AI's suggestions
[ ] I can clearly explain what I'm trying to do
[ ] I can explain what's happening instead
[ ] I can list what I've already tried
[ ] I have my code ready to share
```

If you checked all boxes → Time to ask!

---

## 💬 Question Templates

### For Technical Issues
```
**Goal:** [What you're trying to achieve]

**Problem:** [What's going wrong]

**Error message:** [If any]

**What I've tried:**
- [Try 1]
- [Try 2]

**Code:** [Snippet or file link]

**Question:** [Specific question]
```

### For Direction/Feedback
```
**Project:** [Brief description]

**Current status:** [What you've built so far]

**Question:** [What you're unsure about]

**Context:** [Why you're asking]
```

### For Code Review
```
**Feature:** [What this code does]

**Concerns:** [What you're worried about]

**Code:** [Link or snippet]

**Question:** Is this approach good? Any suggestions?
```

---

## 🎓 Learning Opportunity

Every time you ask your PIC:
1. **Listen to their process** - How do they debug?
2. **Ask "why"** - Understand the reasoning
3. **Take notes** - You might encounter similar issues
4. **Try similar fixes** - Next time you can solve it yourself

**Goal:** Each question should make you more independent!

---

## 👥 Your PICs

**Group 1:** Nanda
**Group 2:** Nathania
**Group 3:** Desi

**They're here to help you succeed!**

Don't be shy - they want you to ask questions. Just make sure you've tried to help yourself first.

---

## Quick Reference

**Ask if:**
- ⏰ Stuck 15+ minutes
- ❓ Tried everything in troubleshooting guide
- 🤔 Need project direction
- 📚 Want best practices advice
- 😰 Feeling overwhelmed

**Try yourself first if:**
- Haven't read error fully
- Haven't asked AI yet
- Haven't checked docs/guides
- Been stuck < 15 minutes
- Haven't tried obvious fixes

**Remember:** Good developers know when to ask for help!
