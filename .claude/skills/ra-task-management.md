# Research Assistant Task Management Skill

This skill provides guidance for effectively managing Research Assistants (RAs) in academic and research settings, based on best practices for clear communication, task delegation, and quality control.

## Core Principles

### 1. Written Task Memos Over Verbal Instructions

Always document complex tasks in writing rather than relying on verbal explanations alone.

**Required elements in every task memo:**
- **Objective**: What needs to be accomplished
- **Importance**: Why this task matters in the broader context
- **Inputs**: Location of source files, data, or reference materials
- **Expected Output**: Format, structure, and quality standards
- **Deadline**: Specific date/time for completion
- **Decision Rules**: How to handle uncertainties without constant back-and-forth
- **Escalation Points**: What requires your approval vs. what they can decide

**Benefits:**
- Reduces misunderstandings and miscommunication
- Minimizes repetitive clarification requests
- Creates reusable documentation for future similar tasks
- Enables smooth handoffs between RAs

### 2. Incremental Task Assignment

Break large projects into smaller, sequential pieces—especially important for new RAs.

**Recommended progression example:**
- Week 1: Sample construction only
- Week 2: Variable definitions and descriptive statistics
- Week 3: Core analysis
- Week 4: Robustness checks and extensions

**Why this works:**
- Early detection of quality issues or misunderstandings
- Allows for course correction before too much time is invested
- Builds RA confidence through early wins
- Provides natural checkpoints for feedback

### 3. Standardized Delivery Format

Require RAs to report using a consistent template:

```
1. What was done
   - Specific tasks completed
   - Key decisions made

2. Output location
   - File paths for all deliverables
   - Naming conventions used

3. Problems encountered
   - Technical issues
   - Data quality concerns
   - Questions that arose

4. Next steps recommended
   - Suggested priorities
   - Open questions to resolve
```

**Impact:** Dramatically reduces management overhead and makes status assessment efficient.

### 4. Contextual Briefing Balance

Provide enough context for good judgment without overwhelming detail.

**Recommended structure:**
1. **Core research question**: The big picture (2-3 sentences)
2. **Task position**: Where this fits in the overall project
3. **Common pitfalls**: Why this step often goes wrong
4. **Definition of done**: Clear criteria for completion

**Avoid two extremes:**
- No context → mechanical, error-prone execution
- Too much context → RA can't distinguish signal from noise

### 5. Reproducibility Standards (Establish Early)

Set up these practices from day one:

**Data Management:**
- Raw data is sacred—never overwrite original files
- Version control for all code (Git or equivalent)
- Documented data cleaning pipelines

**Code Organization:**
- One script per major step
- Master script that runs end-to-end
- Clear folder structure: `raw/`, `clean/`, `temp/`, `output/`, `code/`

**Documentation:**
- Changelog for every update
- README files explaining file purposes
- Comments explaining non-obvious decisions

**Manual Interventions:**
- Any hand-corrections must be documented with justification
- Prefer code-based solutions to manual fixes
- Audit trail for all changes to raw data

## Quick Reference: Task Delegation Checklist

Before assigning a task, verify:
- [ ] Task is broken into manageable pieces
- [ ] Written memo includes all required elements
- [ ] RA understands where this fits in the bigger picture
- [ ] Success criteria are explicit
- [ ] RA knows what they can decide vs. what to escalate
- [ ] Output location and naming are specified
- [ ] Deadline is realistic with buffer time

## Quick Reference: Reviewing Deliverables

When reviewing RA work, check:
- [ ] Output matches expected format
- [ ] Code runs without errors (test the master script)
- [ ] Documentation is complete
- [ ] Decisions are explained
- [ ] Edge cases are handled
- [ ] Results pass sanity checks

## Common Mistakes to Avoid

1. **Micromanaging details** while under-specifying the overall goal
2. **Assigning multiple parallel workstreams** to new RAs before establishing quality baseline
3. **Not documenting decisions** made during verbal discussions
4. **Skipping reproducibility setup** "just this once"
5. **Giving feedback only at completion** rather than at intermediate milestones

## When to Escalate or Adjust Approach

**Signs the current approach isn't working:**
- Repeated similar questions from the RA
- Deliverables consistently miss the mark
- RA seems hesitant to make any decisions
- Code/output is disorganized despite feedback
- Deadlines are frequently missed

**Adjustments to consider:**
- Smaller task chunks
- More explicit examples/templates
- More frequent check-ins
- Pairing with a more experienced RA
- Reviewing whether expectations are realistic
