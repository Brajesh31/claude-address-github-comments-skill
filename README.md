# claude-address-github-comments-skill

A Claude Code skill for reviewing and resolving GitHub pull request comments and review feedback using the GitHub CLI.

## Overview

This skill provides a systematic workflow for collecting review feedback, understanding the requested change, implementing fixes, and responding to reviewers. It helps prevent comments from being missed and keeps the review process traceable.

## Main Capabilities

- Check GitHub CLI authentication.
- Identify the pull request for the current branch.
- Retrieve review comments and issue comments.
- Group feedback by file and topic.
- Distinguish required fixes from suggestions.
- Implement changes in the relevant code.
- Run focused tests and checks.
- Reply to comments with a clear explanation.
- Verify that all requested feedback is addressed.

## Prerequisites

Install GitHub CLI and authenticate:

```bash
gh auth status
```

If authentication is not configured, complete the login process before accessing private repositories.

## Installation

```bash
git clone https://github.com/Brajesh31/claude-address-github-comments-skill.git ~/.claude/skills/address-github-comments
```

## Usage

Invoke the skill when addressing pull request feedback:

```text
/address-github-comments
```

Provide the pull request number or repository context and any constraints on the requested changes.

## Recommended Workflow

1. Confirm the repository and pull request.
2. Retrieve all relevant review and issue comments.
3. Identify unresolved threads.
4. Group comments into implementation tasks.
5. Clarify ambiguous or conflicting feedback.
6. Make focused code changes.
7. Run relevant tests and checks.
8. Inspect the final diff.
9. Reply to each comment with the action taken or a reasoned explanation.
10. Confirm that all required threads are resolved.

## Comment Tracking

| Status | Meaning |
|---|---|
| Pending | Not yet reviewed |
| Understood | Request and impact are clear |
| In progress | Implementation is underway |
| Addressed | Code change or explanation is complete |
| Needs clarification | Feedback is ambiguous |
| Not applicable | Reason documented and communicated |

## Quality Checklist

- No review thread is silently skipped.
- Changes match the reviewer's intent.
- Unrelated code is not modified.
- Tests are run where relevant.
- Replies are factual and concise.
- Unresolved disagreements are documented.
- The final diff is reviewed before pushing.

## Repository Contents

- `SKILL.md`: Main pull request comment workflow.
- `README.md`: Setup, usage, and tracking guidance.

## Practical Principle

Do not mark a comment as addressed just because a reply was posted. Verify the code change, test result, or documented reason actually resolves the concern.
