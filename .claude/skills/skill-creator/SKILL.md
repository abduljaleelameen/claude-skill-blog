---
name: skill-creator
description: Create new Claude Code skills with proper structure and formatting. Use this skill when the user asks to create a new skill, build a skill template, or needs help structuring Claude skills.
---

# Skill Creator Utility

This skill helps you create new Claude Code skills with the correct structure, frontmatter, and content organization. It provides templates, best practices, and validation guidance for building effective skills.

## What Are Claude Skills?

Skills are specialized markdown documents that provide Claude with domain-specific guidance, loaded on-demand when needed. They enable Claude to access expertise contextually without inflating the base system prompt.

## File Structure

Skills use a **SKILL.md file with YAML frontmatter** followed by markdown content:

```markdown
---
name: skill-identifier
description: What the skill does and when Claude should use it
---

# Skill Title

Body content with instructions, examples, and guidance...
```

## Directory Organization

### Project Skills (Recommended for Teams)
```
.claude/skills/skill-name/
└── SKILL.md
```
- Checked into git for team access
- Automatically available after team members pull changes

### Personal Skills
```
~/.claude/skills/skill-name/
└── SKILL.md
```
- For individual workflows and experimental capabilities
- Not shared with teams

### Multi-file Skills
```
skill-name/
├── SKILL.md (required - main skill content)
├── REFERENCE.md (optional - API documentation)
├── EXAMPLES.md (optional - usage examples)
├── scripts/ (optional - utility scripts)
├── assets/ (optional - templates, images)
└── LICENSE.txt (optional - license terms)
```

## Frontmatter Fields

### Required Fields

**name** (required)
- Lowercase identifier using letters, numbers, and hyphens only
- Maximum 64 characters
- Examples: `frontend-design`, `code-reviewer`, `api-tester`

```yaml
name: my-skill-name
```

**description** (required)
- Explains BOTH what the skill does AND when Claude should use it
- Maximum 1024 characters
- Critical for skill discovery—Claude uses this to decide when to activate the skill
- Include trigger terms and use cases

```yaml
description: Create REST API tests with comprehensive coverage. Use this skill when the user asks to test APIs, write API tests, or validate endpoints.
```

### Optional Fields

**allowed-tools** (optional)
- Comma-separated list of tools Claude can use when this skill is active
- Restricts Claude to specific tools for security/safety
- Useful for read-only skills or limited-scope operations

```yaml
allowed-tools: Read, Grep, Glob
```

**license** (optional)
- Reference to license information
- Typically points to LICENSE.txt file

```yaml
license: Complete terms in LICENSE.txt
```

## Content Structure

### Recommended Sections

1. **Overview/Introduction**
   - What the skill enables
   - When to use it
   - Key benefits

2. **Design Thinking/Approach**
   - Conceptual framework
   - How to think about the task
   - Decision-making criteria

3. **Instructions/Guidelines**
   - Step-by-step guidance
   - Best practices organized by category
   - Specific techniques and methods

4. **Examples**
   - Concrete usage examples
   - Code snippets when relevant
   - Different scenarios or use cases

5. **What to Avoid**
   - Anti-patterns
   - Common mistakes
   - Pitfalls to watch out for

### Content Best Practices

**Keep it Concise**
- "The context window is a public good"—only include what Claude genuinely needs
- Aim for SKILL.md under 500 lines
- Move extensive reference docs to REFERENCE.md

**Be Specific**
- Use imperative language ("Do this" not "You might do this")
- Provide concrete examples, not abstract advice
- Include specific tool names, libraries, or techniques

**Stay Focused**
- One capability per skill
- Split broad topics into separate skills
- Each skill should have a clear, singular purpose

**Enable Discovery**
- Write descriptions with trigger terms users might say
- Include context about when Claude should activate the skill
- Think about how users will phrase their requests

## Skill Templates

### Minimal Template
```markdown
---
name: my-skill
description: Brief description of what this skill does and when to use it.
---

# Skill Title

Brief overview of the skill's purpose.

## Guidelines

### Key Concept 1
Specific guidance here.

### Key Concept 2
More specific guidance.

## Examples

Concrete examples showing the skill in action.

## What to Avoid

Anti-patterns and common mistakes.
```

### Read-Only Skill Template
```markdown
---
name: code-analyzer
description: Analyze code quality and provide recommendations. Use when user asks to review, analyze, or audit code.
allowed-tools: Read, Grep, Glob, Bash
---

# Code Analyzer

This skill helps you analyze code for quality, performance, and best practices.

## Analysis Approach

1. Read the relevant files
2. Look for patterns and anti-patterns
3. Provide specific, actionable recommendations
4. Include code examples for improvements

## What to Look For

### Code Quality
- Naming conventions
- Function/method length
- Complexity indicators

### Performance
- Inefficient algorithms
- Memory leaks
- Unnecessary operations

### Best Practices
- Error handling
- Input validation
- Security considerations

## Reporting Format

Provide findings organized by:
- Critical issues (must fix)
- Warnings (should fix)
- Suggestions (nice to have)

## What to Avoid

- Vague feedback without specifics
- Nitpicking style preferences
- Suggesting changes without explaining why
```

### Full-Featured Skill Template
```markdown
---
name: comprehensive-skill
description: Detailed description including what the skill does and specific trigger phrases that indicate when to use it.
---

# Skill Title

Comprehensive overview explaining the skill's purpose, scope, and value.

## Design Thinking

How to approach tasks using this skill:
- Key principles
- Decision-making framework
- Contextual considerations

## Core Guidelines

### Category 1: Specific Area
Detailed guidance for this area with concrete advice.

**DO:**
- Specific action 1
- Specific action 2
- Specific action 3

**DON'T:**
- Anti-pattern 1
- Anti-pattern 2
- Anti-pattern 3

### Category 2: Another Area
More detailed guidance.

### Category 3: Additional Area
Even more guidance.

## Step-by-Step Process

1. **Step One**: What to do first
2. **Step Two**: What comes next
3. **Step Three**: How to complete the task

## Examples

### Example 1: Use Case Name
Concrete example showing the skill in action.

```code
// Example code if applicable
```

### Example 2: Another Use Case
Another example.

## Advanced Techniques

More sophisticated approaches for complex scenarios.

## What to Avoid

- Common mistake 1 and why it's problematic
- Anti-pattern 2 and the better alternative
- Pitfall 3 and how to prevent it

## Remember

Key takeaways and final guidance.
```

## Creating a New Skill: Step-by-Step

### Step 1: Define the Purpose
Ask yourself:
- What specific capability does this skill provide?
- When should Claude activate it?
- What makes this skill necessary (vs. general knowledge)?

### Step 2: Choose a Name
- Use lowercase with hyphens
- Be descriptive but concise
- Examples: `api-tester`, `ui-designer`, `refactoring-assistant`

### Step 3: Write the Description
Include:
- What the skill does
- When Claude should use it
- Trigger phrases users might say

Example: "Create comprehensive API tests with edge case coverage. Use this skill when the user asks to test APIs, write endpoint tests, validate API responses, or create integration tests."

### Step 4: Organize the Content
- Start with an overview
- Provide a thinking framework
- Give specific, actionable guidelines
- Include concrete examples
- List anti-patterns

### Step 5: Decide on Tool Restrictions (Optional)
If this is a read-only skill or should have limited permissions:
```yaml
allowed-tools: Read, Grep, Glob
```

### Step 6: Test the Skill
- Create the skill file in `.claude/skills/skill-name/SKILL.md`
- Try using it in a conversation
- Check if Claude activates it at the right times
- Refine the description and content based on results

## Validation Checklist

Before finalizing your skill, verify:

**Frontmatter:**
- [ ] Name is lowercase, uses hyphens only
- [ ] Name is under 64 characters
- [ ] Description explains what AND when
- [ ] Description is under 1024 characters
- [ ] Includes trigger phrases in description

**Content:**
- [ ] Under 500 lines (or uses separate reference files)
- [ ] Has clear sections with headings
- [ ] Uses specific, actionable language
- [ ] Includes concrete examples
- [ ] Lists anti-patterns or common mistakes
- [ ] Focused on one capability

**File Structure:**
- [ ] Located in `.claude/skills/skill-name/`
- [ ] Primary file named `SKILL.md`
- [ ] Additional files (if any) properly named

**Quality:**
- [ ] No redundant information
- [ ] No conflicts with other skills
- [ ] Clear and concise writing
- [ ] Practical and immediately useful

## Common Skill Types

### Code Quality Skills
- Code reviewers
- Linters and formatters
- Security auditors
- Performance analyzers

### Development Skills
- API testers
- UI/UX designers
- Database optimizers
- Documentation generators

### Specialized Domain Skills
- Data science workflows
- DevOps automation
- Mobile app development
- Game development

### Workflow Skills
- Git commit message formatters
- Pull request creators
- Issue triagers
- Release note generators

## Tips for Effective Skills

**Progressive Disclosure**
- Keep critical info in SKILL.md
- Move reference documentation to REFERENCE.md
- Store scripts separately in `scripts/`
- Use assets folder for templates

**Activation Optimization**
- Test if Claude activates your skill appropriately
- Refine description if it's not triggering when expected
- Add more trigger phrases if needed
- Consider splitting if the skill tries to do too much

**Maintenance**
- Update skills as best practices evolve
- Remove outdated information
- Keep examples current with latest tools/libraries
- Gather feedback from team members

**Documentation**
- Include a README.md in the skill directory explaining usage
- Document any scripts or tools in the skill
- Provide examples of successful outputs

## Example: Creating an API Testing Skill

**Step 1: Purpose**
Help developers create comprehensive REST API tests.

**Step 2: Name**
`api-tester`

**Step 3: Description**
"Create comprehensive REST API tests with edge case coverage. Use this skill when the user asks to test APIs, write API tests, validate endpoints, or create integration tests."

**Step 4: Content Structure**
```markdown
# API Tester

## Testing Approach
- Understand the API specification
- Identify critical paths
- Plan edge cases

## Guidelines
### Test Coverage
- Happy path scenarios
- Error conditions
- Edge cases
- Authentication/authorization

### Test Organization
- Group by endpoint
- Clear test names
- Arrange-Act-Assert pattern

## Examples
[Concrete API test examples]

## What to Avoid
- Testing implementation details
- Incomplete error coverage
- Hard-coded test data
```

**Step 5: Tool Restrictions**
```yaml
allowed-tools: Read, Write, Bash, Grep, Glob
```

## Resources

- Official Documentation: https://code.claude.com/docs/en/skills.md
- Skills Repository: https://github.com/anthropics/skills
- Example Skills: https://github.com/anthropics/claude-code/tree/main/plugins

## Remember

Great skills are:
- **Focused**: One clear purpose
- **Specific**: Concrete guidance, not vague advice
- **Concise**: Respect the context window
- **Discoverable**: Well-written descriptions with trigger terms
- **Practical**: Immediately useful in real workflows

Start simple, test thoroughly, and iterate based on usage. The best skills emerge from real workflows and get refined over time.
