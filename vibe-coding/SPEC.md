# Background
For the whole Q3, AI Forge Business Unit was able to enable all of its 6 team members to actively contribute to the code base even though only 3 of the team members are developers. We did this by leveraging AI code-assistant tools such as Claude Code. Company management is thinking how to replicate this approach to the rest of the employees, where non-engineer employees can leverage AI code assistants to build solutions that solve their pain points, without having to depend on or bother developers/engineers.

# Goal
Three AI Forge team members will be sent to Kuala Lumpur to host a training session for an estimated 17 non-tech employees. By the end of this session, all participants shall:
1. Become comfortable using AI to build custom solutions to solve specific problems or pain points they have.
2. Have good confidence and a strong will to start "vibe coding" (using AI code assistants to build software).
3. Produce an MVP (Minimum Viable Product) or prototype that caters to solving their problems.

# Rules of engagement

## Tools standardization
Considering variation in devices and no guarantee that all participants are "convinced" to adopt this work process, the tools must be standardized:
1. IDE: Visual Studio Code
2. AI Tools: Google Gemini CLI (as it has a generous free tier)

## Project scope
Considering the risks posed and that not all produced solutions will be properly maintained:
1. Deployment: Serverless solution (Netlify or Vercel)
2. Dependency: Each built solution must be able to stand on its own, fully isolated from our company's existing products (ajobthing.my, maukerja.my, ricebowl.my, upbox.ajobthing.my). This means:
   - No direct database connections to existing products
   - No API calls to existing products
   - No shared authentication or user data
   - Cannot perform any CRUD operations (Create, Read, Update, Delete) on existing product data

# Training plan
- Training lasts for 4 days (13 to 16 October 2025)
- Conducted offline in Ajobthing's Kuala Lumpur office

## 13 Oct: Introduction (2-hour class)
**Trainers:** Nanda, Nathania

**Pre-class preparation:** Participants are encouraged to install VS Code and Google Gemini CLI before Day 1 if possible. If unable to install beforehand, setup will be done during the class.

### Agenda
- Introduction to AI Forge's success story and training overview
- Environment setup (VS Code, Google Gemini CLI) - if not done beforehand
- What is "vibe coding" and demo of AI-assisted coding
- Writing a good spec.md (problem statement, requirements, success metrics)
- Participants draft their spec.md and get initial feedback

### Supplemental Materials
See `day1/` folder for:
- Installation guides (VSCode & Gemini CLI for Windows/Mac)
- Troubleshooting guide (execution policy, PATH issues, etc.)
- spec.md template & examples
- AI prompting best practices
- Sample project ideas for inspiration

### Outcomes
- [ ] All required tools are installed on participants' devices and working properly
- [ ] All participants have written a spec.md for their project
- [ ] Each solution has defined success metrics
- [ ] All participants understand how to start vibe-coding

## 14‒15 Oct: Vibe coding (No class - Independent work with PIC support)
All participants will be divided into three groups, with each group having a PIC (Person In Charge).
- **Group 1:** Nanda
- **Group 2:** Nathania
- **Group 3:** Desi

**Important:** Participants must work from the Kuala Lumpur office during Day 2-3. Not attending means forfeiture from the training program.

### PIC Responsibilities
- Be available for participants to ask questions and get unstuck
- Review code and provide guidance on best practices
- Help troubleshoot technical issues
- Ensure participants are making progress toward their goals
- Provide feedback on AI prompting techniques
- Guide participants on scope management (keeping projects achievable)

### Participant Expectations
- Work independently on building their solution using AI code assistants
- Actively engage with their assigned PIC when stuck or needing guidance
- Test their solution locally as they build
- Ask questions proactively rather than staying blocked

### Supplemental Materials
See `day2-3/` folder for:
- Quick reference guide for getting unstuck
- Common coding patterns & examples
- Guidelines on when to ask PIC for help
- Progress checklist

### Outcomes
- [ ] All solutions are functional and tested locally
- [ ] Solutions are ready to be deployed
- [ ] Participants have gained hands-on experience using AI to code
- [ ] Any technical blockers have been resolved with PIC support

## 16 Oct: GitHub & Deployment (2-hour class)
**Trainer:** Nathania

### Agenda
- Introduction to GitHub basics (repositories, commits, push)
- How to push your local project to GitHub
- Connecting GitHub to Netlify/Vercel
- Deploying applications together as a group
- Testing deployed applications
- Q&A and troubleshooting

### Supplemental Materials
See `day4/` folder for:
- GitHub account creation & setup guide
- Git basics cheat sheet (commit, push, pull)
- Step-by-step deployment guide (Netlify & Vercel)
- Deployment troubleshooting guide
- Post-deployment checklist

### Outcomes
- [ ] All participants understand GitHub basics
- [ ] All projects are pushed to GitHub repositories
- [ ] All applications are successfully deployed to Netlify or Vercel
- [ ] Deployed applications are accessible via public URLs
- [ ] Participants know how to update their deployed apps

# Post-Training Support

### Maintenance & Support Plan
- **Ongoing support:** Nanda, Nathania, and Desi remain available for questions via Lark at any time
- **Documentation:** Participants will have access to training materials and resources
- **Community:** Shared Lark group for participants to help each other
- **Q4 2025 focus:** AI Forge will continue enabling more people to use AI code assistant tools

### Success Measurement
Training success will be evaluated based on:
1. **Completion rate:** % of participants who successfully deploy a working solution
2. **Adoption rate:** % of participants who continue using AI code assistants after training
3. **Project metrics:** Whether deployed solutions meet their defined success criteria
4. **Ongoing engagement:** Participant adoption of AI code assistants in Q4 2025
