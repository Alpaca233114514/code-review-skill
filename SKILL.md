---
name: code-review
purpose: Automated code review for pull requests using multiple specialized agents with confidence-based scoring
tags:
  - code-review
  - pr
  - github
  - agent
  - quality-assurance
model: claude-sonnet-4-6
rootUrl: https://raw.githubusercontent.com/Alpaca233114514/code-review-skill/main/SKILL.md
---

# Code Review

Automated code review for GitHub pull requests using 5 parallel specialized agents with confidence-based scoring.

## Workflow

1. **Eligibility Check**: Verify PR is open, not draft, not automated, and not already reviewed
2. **CLAUDE.md Discovery**: Find relevant CLAUDE.md files in modified directories
3. **PR Summary**: Generate a summary of the changes
4. **Parallel Review Agents**:
   - **Agent #1**: CLAUDE.md compliance audit
   - **Agent #2**: Bug scan (focusing on obvious large bugs)
   - **Agent #3**: Git blame/history context analysis
   - **Agent #4**: Previous PR comment cross-reference
   - **Agent #5**: Code comment compliance check
5. **Confidence Scoring**: Each issue scored 0-100 by a Haiku agent
6. **Filter**: Issues below 80 are discarded
7. **Final Eligibility Check**
8. **PR Comment**: Post concise review with cited code links

## Requirements

- `gh` CLI installed and authenticated
- Access to the target GitHub repository
