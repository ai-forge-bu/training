# Frequently Asked Questions (FAQ)

Common questions and answers about the training, tools, and processes.

---

## General Training Questions

### Q: I have no coding experience. Can I still participate?

Yes! This training is designed for non-technical employees. You'll be using AI code assistants to help you build projects. The AI will help write the code - you just need to guide it with clear instructions.

### Q: What if I get stuck?

You have multiple resources:
1. Troubleshooting guides in each day's folder
2. Your assigned PIC (Person In Charge) for your group
3. AI assistant (Google Gemini) to help solve problems
4. Your fellow participants

Don't stay stuck for more than 15 minutes - ask for help!

### Q: How much time should I spend on this during Day 2-3?

Work at your own pace, but plan for:
- Day 2: 4-6 hours of focused work
- Day 3: 4-6 hours of focused work

You can work more or less depending on your project scope and progress.

### Q: What if I can't finish my project?

That's okay! The goal is to learn and build a working MVP (Minimum Viable Product). If you're running short on time:
1. Reduce scope - cut non-essential features
2. Focus on core functionality
3. A simple working app is better than a complex broken one
4. Ask your PIC for help prioritizing

---

## Tool Questions

### Q: Why Google Gemini and not Claude/ChatGPT/Copilot?

Google Gemini has a generous free tier, which means all participants can use it without cost concerns. For future projects, you can use any AI assistant you prefer.

### Q: Can I use a different AI tool?

For the training, we ask everyone to use Google Gemini to standardize the experience. After the training, feel free to use any AI coding assistant you prefer (Claude Code, GitHub Copilot, ChatGPT, etc.).

### Q: Do I need to pay for any tools?

No! All tools used in this training are free:
- Visual Studio Code: Free
- Google Gemini CLI: Free tier
- GitHub: Free account
- Netlify/Vercel: Free tier for deployment

### Q: What if I hit Gemini's free tier limit?

The free tier is quite generous. If you hit the limit:
1. Wait a few minutes between requests
2. Batch your questions
3. Consider signing up for a paid tier if needed (discuss with your manager)

---

## Project Questions

### Q: Can my project connect to our company products (ajobthing.my, etc.)?

No. For security and maintenance reasons, all projects must be standalone and isolated from company products. See the "Project Scope" section in SPEC.md for details.

### Q: Can I build a mobile app?

For this training, stick to web applications (websites). They're easier to deploy and test. After the training, you can explore mobile development on your own.

### Q: Can I work with someone else on the same project?

The training is designed for individual projects to ensure everyone learns. However, you can:
- Help each other when stuck
- Give each other feedback
- Share ideas and approaches

### Q: What if my project idea is too complex?

Simplify it! Break it down into phases:
- Phase 1 (training): Build core features only
- Phase 2 (after training): Add enhanced features
- Phase 3 (future): Add nice-to-have features

Talk to your PIC if you need help scoping your project.

### Q: Can I change my project idea after Day 1?

It's better not to, as you'll lose time. However, if your project is truly unfeasible, talk to your PIC immediately. Better to switch early (Day 1 evening) than midway through Day 2.

---

## Technical Questions

### Q: I'm getting an error I don't understand. What should I do?

Follow this process:
1. Read the error message carefully
2. Copy the full error message
3. Check the troubleshooting guide for your day
4. Ask Google Gemini: "I'm getting this error: [paste error]. Here's my code: [paste code]. How do I fix it?"
5. If still stuck after 15 minutes, ask your PIC

### Q: The AI gave me code but it doesn't work. What do I do?

1. Read the code and try to understand what it does
2. Test it in a simple isolated example
3. Check browser console for errors (F12)
4. Ask the AI: "This code you gave me isn't working. I'm getting [describe problem]. Can you help fix it?"
5. Try a different approach: "Can you show me a simpler way to do this?"

### Q: Should I use a framework like React or stick to plain HTML/CSS/JS?

**If you're new to coding:** Stick to plain HTML/CSS/JavaScript. It's simpler to understand and debug.

**If you have some experience:** You can try React/Vue, but only if you're comfortable with it. Don't learn a new framework during this training.

### Q: How do I save data without a database?

Use `localStorage` - it's a browser feature that saves data locally. See `day2-3/common-patterns.md` for examples. Note: Data only persists on that specific browser/device.

### Q: Can I use external APIs?

Yes, but:
1. Use free APIs only
2. Make sure they don't require complex authentication
3. Don't use APIs from our company products
4. Have a backup plan if the API is down

---

## Deployment Questions

### Q: Which is better, Netlify or Vercel?

Both are excellent. Choose based on:
- **Netlify:** Slightly simpler, great for static HTML/CSS/JS sites
- **Vercel:** Better for React/Next.js, slightly more features

You can't go wrong with either!

### Q: Do I need a custom domain name?

No. Both Netlify and Vercel provide free subdomains:
- Netlify: `your-project.netlify.app`
- Vercel: `your-project.vercel.app`

These are perfect for the training and for sharing your project.

### Q: What if deployment fails?

1. Read the error message in the deployment logs
2. Check `day4/deployment-troubleshooting.md`
3. Common issues: missing files, wrong build settings, environment variables
4. Ask your PIC with: deployment logs + GitHub repo link

### Q: Can I deploy the same project to both Netlify and Vercel?

Yes! You can deploy to both if you want. It's good practice to see how each platform works.

### Q: How do I update my deployed site?

Just push to GitHub:
```bash
git add .
git commit -m "Update feature"
git push
```

Both Netlify and Vercel automatically rebuild and deploy when you push to GitHub.

---

## Post-Training Questions

### Q: What happens to my project after the training?

It's yours! Your project will remain deployed and accessible as long as:
- You don't delete the GitHub repository
- You don't delete the Netlify/Vercel project
- You stay within the free tier limits

### Q: Can I continue developing my project after the training?

Absolutely! That's encouraged. Continue improving it:
- Add features you didn't have time for
- Improve the design
- Share it with your team
- Use it to solve your actual work problems

### Q: Will there be ongoing support after the training?

Yes, ongoing support:
- Nanda, Nathania, and Desi available via Lark at any time
- Lark community group for questions and peer support
- Q4 2025: AI Forge will continue enabling more people to use AI code assistants

### Q: Can I build more projects using this approach?

Yes! That's the whole goal. You now have the skills to:
- Build tools for your own pain points
- Automate repetitive tasks
- Create custom solutions for your team

Keep building!

### Q: What if my project needs maintenance or breaks?

You're responsible for your project. If it breaks:
1. Check the error
2. Use AI to help fix it
3. Ask in the Lark community group
4. Reach out to Nanda, Nathania, or Desi if needed

---

## AI and Prompting Questions

### Q: How do I know if the AI-generated code is good?

Ask yourself:
1. Does it work?
2. Do I understand what it does?
3. Is it readable?
4. Does it follow best practices?

If unsure, ask the AI: "Is this code following best practices? Are there any security concerns?"

Or ask your PIC for a code review.

### Q: The AI keeps giving me wrong code. What do I do?

1. Make your prompts more specific
2. Provide more context
3. Break down the problem into smaller pieces
4. Try asking in a different way
5. Sometimes AI makes mistakes - try a different approach

See `day1/prompting-best-practices.md` for tips.

### Q: Can I copy code from the internet?

Yes, but:
1. Understand what it does
2. Make sure it's not copyrighted or proprietary
3. Adapt it to your needs
4. Prefer asking AI to explain and generate code for you

### Q: Should I trust everything the AI tells me?

No! AI is a tool, not an authority. Always:
- Test the code
- Verify it works
- Question things that don't make sense
- Cross-reference with documentation if unsure

---

## Success and Evaluation

### Q: How will the training success be measured?

Based on:
1. Completion rate: Did you deploy a working project?
2. Learning: Can you explain what you built?
3. Confidence: Do you feel comfortable building more projects?
4. Adoption: Will you continue using AI code assistants?

### Q: What if I don't successfully deploy by Day 4?

That's okay! The process and learning are more valuable than the end result. We'll help you:
- Understand what blocked you
- Finish deployment after the training
- Learn from the experience

### Q: Is there a presentation or demo at the end?

Not formally required, but you'll share:
- Your deployed URL
- What you built
- What you learned
- Challenges you faced

Informal sharing, not a formal presentation.

---

## Troubleshooting Questions

### Q: My question isn't answered here. What do I do?

1. Check the relevant day's materials (day1/, day2-3/, day4/)
2. Check troubleshooting guides
3. Ask Google Gemini
4. Ask your PIC
5. Post in the Lark training group

### Q: Who do I contact for what?

**Technical issues (setup, coding, deployment):**
- Your assigned PIC

**Training logistics (schedule, location):**
- Nanda or Nathania

**Tool access issues (GitHub, Gemini, etc.):**
- Your PIC first, then IT if needed

**Project scope questions:**
- Your PIC

---

## Common Concerns

### Q: I feel overwhelmed. Is this normal?

Yes, completely normal! You're learning new skills. Remember:
- You don't need to understand everything
- Progress over perfection
- Your PIC is here to help
- Take breaks when needed
- Focus on one small task at a time

### Q: Everyone else seems to be doing better than me.

Don't compare! Everyone:
- Has different backgrounds
- Works at different paces
- Faces different challenges
- Is learning different things

Focus on your own progress and learning.

### Q: I don't think I can finish in time.

Talk to your PIC immediately. Options:
- Reduce project scope
- Prioritize core features
- Get help with blocking issues
- Adjust timeline expectations

Better to finish a simple working project than a complex broken one.

---

## Resources

**During Training:**
- Day-specific folders (day1/, day2-3/, day4/)
- Your PIC
- AI assistant (Gemini)
- Fellow participants

**After Training:**
- Lark community group
- Nanda, Nathania, and Desi (available anytime)
- This FAQ
- Online resources (listed in RESOURCES.md)

---

## Still Have Questions?

If your question isn't answered here:
1. Ask your PIC
2. Post in the Lark training group
3. Ask during the training sessions

**Remember: No question is too simple or too basic. Ask!**
