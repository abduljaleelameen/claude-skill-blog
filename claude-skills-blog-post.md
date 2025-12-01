# Claude Skills: Teaching Your AI Assistant Superpowers

> *What if your AI assistant could learn exactly how YOU work?*

---

## How to Read This Article

| Reader Type | Start Here | Focus On |
|-------------|------------|----------|
| **Complete Beginner** | Start from the top, read everything | The analogies and "Real-World" sections |
| **Business Professional** | Jump to "What Are Claude Skills?" | The Before/After section and use cases |
| **Technical User** | Skip to "Your First Skill" | The code examples and advanced sections |
| **In a Hurry?** | Read the TL;DR Summary at the end | Key takeaways in 2 minutes |

---

## What You Will Learn

By the end of this article, you will be able to:

- **Understand** what Claude Skills are (no technical background needed)
- **Create** your first simple skill in under 5 minutes
- **Recognize** when skills will save you time vs. other options
- **Apply** best practices used by professionals
- **Find** resources to go deeper when ready

**Time to read:** 15-20 minutes (or 2 minutes for the TL;DR)

---

Meet Alex, a developer who spent 30 minutes every day re-explaining the same coding standards, file structures, and company conventions to Claude. Day after day, the same frustrating routine. Then one day, everything changed...

![Claude Skills Overview](images/claude-skills-overview.drawio.svg)
*Figure 1: The transformation equation - Regular Claude + Your Skills = YOUR personalized AI superpower*

The visual above captures a simple but powerful truth: when you combine Claude's capabilities with your custom skills, you don't just get an AI assistant — you get YOUR AI assistant. But what exactly IS a skill? Let's peek inside the recipe card...

---

## The Story Begins: A Developer's Frustration

Imagine this: You're a developer named Alex. Every day, you ask Claude to help you write code, but there's a catch. Your company has specific coding standards, a unique file structure, and particular ways of doing things. Every. Single. Time. You have to explain these rules to Claude.

*"Remember, we use camelCase for variables..."*
*"Don't forget our error handling pattern..."*
*"We always add these specific comments..."*

Sound familiar?

**What if Claude could just... remember?** What if you could teach Claude your rules ONCE, and it would apply them forever?

Welcome to **Claude Skills** — the game-changer that transforms Claude from a general-purpose AI into YOUR personalized AI assistant.

---

### Real-World Examples: It is Not Just for Developers

> **This section is for: Everyone** — See how skills apply to YOUR work

**Sarah the Marketer:**
Sarah writes 10 blog posts per month for her company. Every time, she reminds Claude about their brand voice, forbidden words, preferred phrases, and formatting rules. With a "brand-voice" skill, she writes one set of instructions and Claude follows them automatically. **Result: 2 hours saved per week.**

**David the Executive:**
David needs weekly reports summarized in a specific format for board meetings. Instead of reformatting every report, his "executive-summary" skill transforms any document into his preferred bullet-point style with exactly the right level of detail. **Result: 15 minutes saved per report.**

**Maya the Teacher:**
Maya creates lesson plans following her school's template. Her "lesson-planner" skill ensures every plan includes learning objectives, materials, activities, and assessments in the right format. **Result: Creates plans 3x faster.**

---

## What Are Claude Skills? (The Simple Explanation)

Think of Claude Skills like **recipes for your AI chef**.

| Without Skills | With Skills |
|----------------|-------------|
| You describe every ingredient and step each time | Claude follows your saved recipe automatically |
| Generic responses | Personalized, consistent outputs |
| Repeating yourself constantly | "Just do it the usual way" |

> **In Plain English:** A skill is simply a text file that tells Claude how to do a specific task YOUR way. No coding required for basic skills.

> **In one sentence:** Skills are instruction folders that teach Claude how to perform specific tasks YOUR way.

### The Recipe Analogy

Imagine you're teaching someone to make your grandmother's famous cookies:

- **Without a recipe:** *"Okay, so first you need flour... how much? Um, about this much... and then sugar, but not too much..."*
- **With a recipe:** *"Follow the recipe card. It has everything."*

Claude Skills ARE those recipe cards for AI tasks. Now let's look inside one of these recipe cards to see what makes a skill tick...

---

Think of a skill as a recipe card. But instead of ingredients for cookies, it contains instructions for AI behavior. Here's what's inside:

![Skill Anatomy Diagram](images/skill-anatomy.drawio.svg)
*Figure 2: Anatomy of a Claude Skill — The building blocks that make up every skill*

Every skill has three core components: **metadata** (the name and description that tell Claude when to use it), **instructions** (the step-by-step guidance for behavior), and **optional resources** (supporting files, examples, and scripts). Now you see the structure, but how does Claude know WHEN to pull out this recipe card?

> **Jargon Buster: Metadata**
> Metadata is just "information about information." In a skill, it is the name and description at the top of the file — like the title and summary on a recipe card.

---

## Your First Skill: Hello World (5 Lines!)

> **This section is for: Anyone ready to try** — No programming experience needed

Let's start with the simplest possible skill. Don't worry — it's easier than you think!

### The Simplest Skill Ever

Create a folder called `my-first-skill/` and add one file called `SKILL.md`:

```markdown
---
name: friendly-greeter
description: Greets users in a friendly, enthusiastic way
---

# Friendly Greeter

Always greet users with warmth and enthusiasm. Use their name if provided.
End every greeting with an encouraging message about their day.
```

**That's it!** You just created your first Claude Skill.

> **Jargon Buster: YAML Frontmatter**
> Those lines between the `---` marks at the top? That is called "frontmatter." Think of it as a form you fill out: name goes here, description goes here. The dashes just mark where the form starts and ends.

> **What just happened?**
>
> - `name`: A unique identifier (lowercase, hyphens only)
> - `description`: Tells Claude WHEN to use this skill
> - The markdown content: Tells Claude HOW to behave

### Try It Now: Your 2-Minute Challenge

1. Open any text editor (Notepad, TextEdit, VS Code — anything works)
2. Copy the skill above
3. Save it as `SKILL.md` in a new folder
4. Upload to Claude.ai and test it!

**What to say to test:** "Hello, I'm [your name]!"

---

## How Does Claude Know When to Use a Skill?

This is where the magic happens. Claude uses something called **Progressive Disclosure** — a fancy term for a simple idea:

> **Jargon Buster: Progressive Disclosure**
> This just means "don't show everything at once." Like a restaurant menu: you see dish names first, then details only for what you order. Claude sees skill names first, then reads the full instructions only when needed.

### The "Need to Know" System

Imagine Claude's memory as a smart filing cabinet. It doesn't read every file every time — that would be like reading an entire cookbook just to boil water! Instead, Claude uses a layered approach...

![Progressive Disclosure Diagram](images/progressive-disclosure.drawio.svg)
*Figure 3: Progressive Disclosure — Claude's intelligent three-level memory system*

Think of it like a filing cabinet:

| Level | What Claude Sees | When | Real-World Comparison |
|-------|-----------------|------|----------------------|
| **Level 1: Labels** | Just skill names & descriptions | Always (in the drawer labels) | Like reading book titles on a shelf |
| **Level 2: Files** | Full SKILL.md content | When a skill seems relevant | Like opening a book to the table of contents |
| **Level 3: Details** | Supporting files, scripts, templates | Only when actively using the skill | Like reading the actual chapters |

### Why This Matters

Imagine if Claude had to read EVERY skill instruction for EVERY conversation. It would be like reading an entire cookbook just to boil water!

Instead, Claude:

1. Glances at the "menu" (skill descriptions)
2. Opens the relevant "recipe" (SKILL.md)
3. Checks additional notes only if needed (supporting files)

**Result:** Fast, efficient, and contextually aware responses.

This "need-to-know" system explains efficiency. But what happens at the moment of decision? When you ask Claude a question, a split-second decision happens behind the scenes. Here's the flowchart your AI follows:

---

![Skill Activation Flow](images/skill-activation-flow.drawio.svg)
*Figure 4: The Decision Flowchart — How Claude decides to activate a skill in real-time*

Understanding the decision process reveals how to craft skills that trigger reliably. Notice how the description is the key — it's what Claude uses to match your request to the right skill. Now let's explore what kinds of skills you can build...

---

## Building Better Skills: From Basic to Advanced

> **This section is for: Technical users and curious learners** — Contains code examples

Now that you understand the basics, let's level up!

### Level 2: A Practical Skill (Task Automation)

Here's a skill that automatically formats code review comments:

```markdown
---
name: code-reviewer
description: Formats code review feedback in a structured, constructive way. Use when reviewing code or providing feedback on pull requests.
---

# Code Review Assistant

## Your Role
You are a constructive code reviewer focused on helping developers improve.

## Response Format
Always structure feedback as:

### What Works Well
- List positive aspects first
- Be specific about good patterns

### Suggestions for Improvement
- Frame as questions when possible ("Have you considered...?")
- Explain the WHY behind each suggestion
- Provide code examples

### Priority
Rate each suggestion: [Critical] | [Recommended] | [Nice-to-have]

## Tone Guidelines
- Be encouraging, not discouraging
- Focus on the code, not the coder
- Assume good intent
```

> **Pro Tip:** Notice how specific the instructions are? The more detailed your skill, the more consistent Claude's output!

---

### Level 3: Skill with Supporting Files

For complex skills, you can include additional files:

```
brand-voice-writer/
├── SKILL.md
├── tone-guide.md
├── vocabulary.md
└── examples/
    ├── good-example.md
    └── bad-example.md
```

**SKILL.md:**

```markdown
---
name: brand-voice-writer
description: Writes content matching company brand voice and guidelines. Use for marketing copy, blog posts, and customer communications.
---

# Brand Voice Writer

## Core Instructions
Write all content following our brand voice guidelines.

## References
- See `tone-guide.md` for voice and tone rules
- See `vocabulary.md` for approved/forbidden terms
- Check `examples/` for real samples

## Process
1. Review the content request
2. Check tone guide for appropriate style
3. Use only approved vocabulary
4. Match examples in the examples folder
```

Every skill lives in a folder — your AI's personal knowledge base. Here's how to organize it like a pro:

![Skill Directory Structure](images/skill-directory-structure.drawio.svg)
*Figure 5: Skill Folder Structure — A well-organized skill directory with all its components*

With structure understood, let's see how skills work across different Claude platforms...

---

### Level 4: Advanced Skill with Scripts

> **This section is for: Technical users comfortable with programming**

For power users, skills can include executable code!

```
data-analyzer/
├── SKILL.md
├── scripts/
│   ├── parse_csv.py
│   └── generate_chart.py
└── templates/
    └── report_template.md
```

**SKILL.md:**

```markdown
---
name: data-analyzer
description: Analyzes CSV data files and generates visual reports. Use when user wants to analyze spreadsheet data or create charts.
---

# Data Analysis Expert

## Capabilities
- Parse and analyze CSV files
- Generate statistical summaries
- Create visualizations

## Available Scripts
- `scripts/parse_csv.py` - Data parsing and cleaning
- `scripts/generate_chart.py` - Chart generation

## Workflow
1. Accept data file from user
2. Run parse_csv.py to clean and structure data
3. Analyze patterns and generate insights
4. Use generate_chart.py for visualizations
5. Format final report using templates/report_template.md

## Output Format
Always deliver:
- Executive summary (3 bullet points)
- Key findings with visualizations
- Recommended actions
```

---

## The Skill Universe: What Can You Build?

Skills aren't one-size-fits-all. They span three exciting kingdoms, each with its own superpowers:

![Skill Categories Diagram](images/skill-categories.drawio.svg)
*Figure 6: The Three Kingdoms of Claude Skills — Creative, Technical, and Enterprise domains*

From creative arts to enterprise automation, the possibilities are vast. Let's explore each kingdom:

### Creative Skills

| Skill | What It Does | Who Uses It |
|-------|--------------|-------------|
| `algorithmic-art` | Generates art using p5.js particle systems | Artists, designers |
| `canvas-design` | Creates visual designs in PNG/PDF | Marketing teams |
| `slack-gif-creator` | Makes optimized animated GIFs | Social media managers |

### Technical Skills

| Skill | What It Does | Who Uses It |
|-------|--------------|-------------|
| `artifacts-builder` | Builds React/Tailwind UI components | Developers |
| `mcp-builder` | Creates MCP server integrations | Backend engineers |
| `webapp-testing` | Automates Playwright UI tests | QA teams |

> **Jargon Buster: MCP Servers**
> MCP (Model Context Protocol) is a way for Claude to connect to external tools and databases. Think of it like giving Claude permission to use specific apps on your computer. You do not need MCP for basic skills.

### Enterprise Skills

| Skill | What It Does | Who Uses It |
|-------|--------------|-------------|
| `brand-guidelines` | Applies corporate branding | Marketing, Communications |
| `internal-comms` | Writes newsletters and reports | HR, Internal comms |
| `theme-factory` | Generates professional themes | Design teams |

### Document Skills (Production-Grade)

| Skill | What It Does | Who Uses It |
|-------|--------------|-------------|
| `docx` | Creates/edits Word documents | Everyone |
| `pdf` | Extracts, merges, fills PDF forms | Admin, Legal |
| `pptx` | Builds PowerPoint presentations | Sales, Executives |
| `xlsx` | Works with Excel spreadsheets | Analysts, Finance |

But how do you organize all these skill files? And where can you use them?

---

## Where Do Skills Work?

One skill. Three platforms. Endless possibilities. Build once, use everywhere:

![Skill Ecosystem Diagram](images/skill-ecosystem.drawio.svg)
*Figure 7: The Claude Skills Ecosystem — Your skills travel with you across all platforms*

| Platform | How to Use Skills | Best For |
|----------|------------------|----------|
| **Claude.ai** | Upload skill folders directly in web interface | Quick testing, personal use |
| **Claude Code** | Install via plugins or local `.claude/skills/` folder | Development, automation |
| **Claude API** | Reference skills in API calls | Custom applications |

> **The Power of Portability:** Create a skill once, use it across ALL Claude platforms. Your personalized AI travels with you!

The portability is powerful. But what does this transformation actually look like in practice? Let's witness the before and after...

---

## Before & After: The Transformation

Let's witness the transformation. Same request. Two completely different experiences:

![Before After Comparison](images/before-after-skills.drawio.svg)
*Figure 8: The dramatic difference — 30 minutes of frustration vs. 2 minutes of perfection*

### Without Skills (Before)

**User:** "Write me a blog post about AI"

**Claude:** *Writes a generic, formal article about artificial intelligence...*

**User:** "No, make it more casual, add some humor, use our company voice..."

**Claude:** *Rewrites... still not quite right...*

**User:** "Ugh, let me explain our style guide again..."

*— 30 minutes later, still iterating —*

---

### With Skills (After)

**User:** "Write me a blog post about AI"

**Claude:** *[Automatically loads brand-voice-writer skill]*

*Writes a perfectly on-brand article with the right tone, vocabulary, and format on the first try!*

**User:** "Perfect! Exactly what I needed."

*— 2 minutes total —*

The difference is dramatic. Ready to create this magic for yourself?

---

## Creating Your First Real Skill: Step-by-Step

Ready to build something useful? Let's create a **Meeting Notes Formatter** skill together! Creating your first skill is simpler than you think. Follow this roadmap from idea to implementation:

![Skill Creation Workflow](images/skill-creation-workflow.drawio.svg)
*Figure 9: The Skill Creation Workflow — Your roadmap from idea to implementation*

### Step 1: Identify the Gap

Ask yourself:

- What task do I repeat often?
- Where do I keep re-explaining things to Claude?
- What would save me the most time?

### Step 2: Create the Folder Structure

```bash
mkdir meeting-notes-formatter
cd meeting-notes-formatter
touch SKILL.md
```

> **Non-Technical Alternative:** Just create a new folder on your computer, name it `meeting-notes-formatter`, and create a new text file inside called `SKILL.md`

### Step 3: Write the SKILL.md

```markdown
---
name: meeting-notes-formatter
description: Transforms messy meeting notes into structured, actionable summaries. Use when processing meeting transcripts, raw notes, or voice memo transcriptions.
---

# Meeting Notes Formatter

## Your Mission
Transform chaotic meeting notes into clear, actionable documents.

## Output Structure

### Meeting Summary
**Date:** [Extract or ask]
**Attendees:** [List all mentioned names]
**Duration:** [If mentioned]

### Key Decisions Made
- List each decision as a bullet point
- Include WHO made the decision if mentioned

### Action Items
| Task | Owner | Deadline |
|------|-------|----------|
| [Task description] | [Person responsible] | [Due date if mentioned] |

### Key Discussion Points
Summarize main topics discussed (3-5 bullet points)

### Open Questions
List any unresolved questions or items needing follow-up

### Next Steps
What happens next? When is the next meeting?

## Formatting Rules
- Use clear headers for visual scanning
- Keep summaries concise (no fluff!)
- If information is missing, mark as [TBD] and note it
- Always end with "Action Items" as the last major section

## Tone
Professional but approachable. Write for busy people who need quick answers.
```

### Step 4: Test and Iterate

Use your skill with real meeting notes. Refine based on output:

- Too verbose? → Add "Keep summaries under X words"
- Missing info? → Add prompts for Claude to ask
- Wrong format? → Provide explicit examples

### Step 5: Share or Deploy

- **Personal use:** Drop in `~/.claude/skills/`
- **Team use:** Commit to shared repository
- **Community:** Share on GitHub with the tag `claude-skills`

You have the workflow. But when should you use a skill versus other customization options?

---

## Self-Assessment: Is a Skill Right for You?

**Answer these questions to find out:**

| Question | Yes | No |
|----------|-----|-----|
| Do I repeat the same instructions to Claude more than twice a week? | **Skill will help** | Maybe not needed yet |
| Do I need consistent output format every time? | **Skill will help** | Custom instructions may be enough |
| Does my task involve multiple steps or rules? | **Skill will help** | Simple prompt may work |
| Do I want to share my Claude setup with teammates? | **Skill is perfect** | Personal settings work fine |
| Do I need Claude to access external databases or APIs? | **Consider MCP instead** | Skill is fine |

**Scoring:**

- **3+ "Skill will help"** → You should definitely create a skill
- **1-2 "Skill will help"** → A skill could help, but start simple
- **0 "Skill will help"** → You might be fine with basic prompts for now

---

## Best Practices: The Pro Tips

After researching dozens of skills and official documentation, here are the golden rules:

### Writing Descriptions

| Do | Do Not |
|-------|---------|
| Write in third person | Use "you" or "I" |
| Be specific about triggers | Be vague |
| Include file types/keywords | Assume Claude knows |

**Good:** *"Processes Excel files (.xlsx) and generates summary reports with charts."*

**Bad:** *"You can use this to work with spreadsheets."*

### Organizing Content

| Do | Do Not |
|-------|---------|
| Use progressive disclosure | Put everything in SKILL.md |
| Reference external files | Bloat the main file |
| Keep SKILL.md under 400 lines | Write a novel |

### Troubleshooting

| Problem | Solution |
|---------|----------|
| Skill doesn't trigger | Add more explicit keywords to description |
| Inconsistent outputs | Tighten output spec, add examples |
| Too slow | Move details to referenced files |

---

## Skills vs. Alternatives: When to Use What

Claude offers multiple ways to customize its behavior. Here's your decision compass:

![Skills vs Alternatives](images/skill-vs-alternatives.drawio.svg)
*Figure 10: Decision Matrix — Choose the right tool for your customization needs*

| Feature | Skills | MCP Servers | Custom Instructions |
|---------|--------|-------------|-------------------|
| **Best For** | Repeatable workflows | External API integrations | Simple preferences |
| **Complexity** | Medium | High | Low |
| **Portability** | High (works everywhere) | Requires setup | Limited |
| **Code Required** | Optional | Yes | No |
| **Dynamic Data** | Limited | Yes | No |

### Plain Language Comparison

| If You Want To... | Use This |
|-------------------|----------|
| "I want Claude to always know my name and role" | **Custom Instructions** (simplest) |
| "I want Claude to follow my company's writing style" | **Skill** |
| "I want Claude to format all my emails the same way" | **Skill** |
| "I need Claude to check my calendar and schedule meetings" | **MCP Server** (connects to external tools) |
| "I need Claude to query my company database" | **MCP Server** |
| "I want Claude to handle complex multi-step projects" | **Skill + Subagents** |

### Quick Decision Guide

- **"I want Claude to follow my company's writing style"** → Skill
- **"I need Claude to access my database"** → MCP Server
- **"I just want Claude to know my name"** → Custom Instructions
- **"I need an autonomous agent for complex tasks"** → Subagents + Skills

With this matrix, you can choose the right tool for every situation.

---

## The Future of AI Customization

Claude Skills represent a fundamental shift in how we interact with AI:

> **From "one-size-fits-all" to "built-for-you"**

### What's Coming Next?

Based on Anthropic's trajectory and community development:

1. **Skill Marketplaces** — Download pre-built skills from verified creators
2. **Skill Chains** — Skills that automatically call other skills
3. **Learning Skills** — Skills that improve based on your feedback
4. **Team Skill Sync** — Real-time skill sharing across organizations

### The Bigger Picture

We're moving toward a world where:

- Your AI assistant truly KNOWS you
- Repeated tasks become one-click operations
- Teams share institutional knowledge through skills
- AI customization is as easy as installing an app

---

## TL;DR Summary (The 2-Minute Version)

**In a hurry? Here is everything you need to know:**

### What Are Skills?

Text files that teach Claude to do specific tasks YOUR way. Like recipes for your AI chef.

### Why Use Them?

- Stop repeating yourself (save 30+ minutes daily)
- Get consistent, on-brand outputs every time
- Share your Claude setup with your team

### The Simplest Skill (Copy This!)

```markdown
---
name: my-skill-name
description: What this skill does and when to use it
---

# Instructions for Claude

Your rules and guidelines here.
```

### Where to Put Skills

- **Claude.ai:** Upload the folder
- **Claude Code:** Put in `.claude/skills/` folder
- **API:** Reference in your calls

### 3 Things to Remember

1. The **description** is crucial — it tells Claude WHEN to use the skill
2. Be **specific** in your instructions — vague = inconsistent
3. Start **simple** — you can always add complexity later

### Next Step

Pick ONE repetitive task and create a skill for it. Start small. Iterate.

---

## Ready to Start? Your Next Steps

> **You've got this!** Everyone starts somewhere. The best skill creators began exactly where you are now.

### Beginner Path

1. Create the simple greeter skill from this article
2. Use it in Claude.ai to see it work
3. Modify it — change the instructions, see what happens

### Intermediate Path

1. Identify your most repetitive Claude task
2. Build a skill for it using the meeting notes template
3. Iterate based on results

### Advanced Path

1. Explore the [official skills repository](https://github.com/anthropics/skills)
2. Study the document skills (docx, pdf, etc.) for complex patterns
3. Build skills with scripts for your specific workflows

---

## Resources & References

### Official Sources

- [Anthropic Skills Repository](https://github.com/anthropics/skills) — Official examples
- [Claude Code Skills Documentation](https://docs.claude.com/en/docs/claude-code/skills) — Technical docs
- [Skill Authoring Best Practices](https://docs.claude.com/en/docs/agents-and-tools/agent-skills/best-practices) — Pro tips
- [Anthropic Engineering: Agent Skills](https://www.anthropic.com/engineering/equipping-agents-for-the-real-world-with-agent-skills) — Deep dive

### Community Resources

- [Awesome Claude Skills](https://github.com/travisvn/awesome-claude-skills) — Curated list
- [Claude Skills Collection](https://github.com/abubakarsiddik31/claude-skills-collection) — Community skills
- [Claude Code Plugins Plus](https://github.com/jeremylongshore/claude-code-plugins-plus) — 243+ plugins

### Tutorials & Courses

- [Anthropic Academy: Claude Code in Action](https://anthropic.skilljar.com/claude-code-in-action) — Official course
- [DataCamp: Claude Code Tutorial](https://www.datacamp.com/tutorial/claude-code) — Hands-on guide
- [Skywork: Step-by-Step Tutorial](https://skywork.ai/blog/ai-agent/how-to-create-claude-skill-step-by-step-guide/) — Beginner friendly

### Articles & Deep Dives

- [Claude Skills Deep Dive](https://leehanchung.github.io/blogs/2025/10/26/claude-skills-deep-dive/) — First principles analysis
- [Why Agent Skills Will Transform AI](https://alirezarezvani.medium.com/why-agent-skills-will-transform-how-we-build-ai-32daee24fc8a) — Vision piece
- [Claude Skills Explained (Lenny's Newsletter)](https://www.lennysnewsletter.com/p/claude-skills-explained) — Workflow guide

---

## Final Thoughts

Claude Skills aren't just a feature — they're a philosophy. The idea that AI should adapt to YOU, not the other way around.

Whether you're a developer tired of repeating yourself, a marketer ensuring brand consistency, or a curious mind exploring AI's possibilities, skills open a new door.

**The question isn't "What can Claude do?"**

**It's "What will you teach Claude to do?"**

---

*Start building. Start teaching. Start transforming.*

*Your AI superpower awaits.*

---

**Share this article** if you found it helpful!

**Questions?** Drop them in the comments below.

**Built something cool?** Tag your skill with `#ClaudeSkills` on GitHub!

---

*Last updated: December 2025*
*Based on research from 24+ sources including official Anthropic documentation, community repositories, and technical deep dives.*
