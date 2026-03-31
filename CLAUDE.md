# Claude Code Guidelines

## Project Overview

This repository is the main task assignment hub for Research Assistants (RAs) and community contributors working on OperationsPAI - an open-source community building the world's first self-evolving training environment for Root Cause Analysis (RCA) in microservices.

## Language Policy

**All content in this repository must be in English only.** No Chinese characters should appear in:
- Issue templates
- Documentation
- Code comments
- Commit messages
- Pull request descriptions

## Task Assignment Workflow

When creating tasks for RAs or community members:

1. Use the "Task Assignment" issue template
2. Follow the structured format (Objective, Background, Input, Output, Timeline, Decision Rules, Definition of Done)
3. Break complex tasks into smaller, sequential pieces
4. Set realistic deadlines with buffer time
5. Define clear escalation points (what they can decide vs. what to ask)

## Progress Reporting Format

RAs should report progress using this structure:

```markdown
### What was done
- Completed items

### Output location
- File paths and links

### Problems encountered
- Technical issues or blockers

### Next steps recommended
- Suggested priorities
```

## Reproducibility Requirements

All code and data work must follow these standards:

- Raw data is never modified (use `clean/` or `processed/` directories)
- One script per major step
- Master script runs end-to-end
- Clear folder structure: `raw/`, `clean/`, `temp/`, `output/`, `code/`
- Document all manual corrections
- Maintain a changelog

## Communication Guidelines

- Be concise and specific in task descriptions
- Provide context for why tasks matter
- Highlight common pitfalls
- Define "done" clearly
- Use checklists for deliverables

## Code Style

- Write clear, self-documenting code
- Use meaningful variable names
- Add comments for non-obvious decisions
- Follow existing project conventions

## Review Checklist

Before marking a task complete:

- [ ] Output matches expected format
- [ ] Code runs without errors
- [ ] Documentation is complete
- [ ] Decisions are explained
- [ ] Edge cases are handled
- [ ] Results pass sanity checks
