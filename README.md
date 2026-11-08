# Address GitHub Comments Skill

A structured skill for reviewing GitHub pull-request feedback, converting comments into clear implementation tasks, making focused fixes, and responding with accurate status updates.

The goal is to address every actionable review thread without losing context, changing unrelated code, or marking unresolved feedback as complete.

## What This Skill Helps With

- Confirm GitHub CLI authentication and repository context.
- Identify the pull request for the current branch.
- Retrieve issue comments and review feedback.
- Separate unresolved feedback from already addressed threads.
- Group comments by file, topic, and dependency.
- Identify ambiguous or conflicting requests.
- Prepare an implementation plan.
- Apply focused changes after review.
- Run relevant tests and inspect the final diff.
- Reply to reviewers with a concise and accurate summary.
- Track thread resolution through completion.

## When to Use It

Use this skill when responding to pull-request review comments, resolving issue feedback, handling requested changes, or preparing a systematic review-response pass before merging.

It is useful when a pull request has multiple reviewers, several files, or comments that need to be grouped into related implementation work.

## Prerequisites

Install GitHub CLI and authenticate:

~~~bash
gh auth status
~~~

If authentication is not configured:

~~~bash
gh auth login
~~~

Confirm that the authenticated account has permission to view and update the target pull request. Review the repository's contribution and branch-protection rules before pushing changes.

## Installation

~~~bash
git clone https://github.com/Brajesh31/claude-address-github-comments-skill.git ~/.claude/skills/address-github-comments
~~~

## Invocation

~~~text
/address-github-comments
~~~

Provide the repository context or pull-request number, the branch under review, and any constraints on which changes may be made.

## Recommended Workflow

### 1. Verify context

Confirm the repository, current branch, pull request, base branch, and GitHub CLI authentication. Do not assume the current directory belongs to the intended pull request.

### 2. Collect feedback

Retrieve review comments, issue comments, and unresolved review threads. Distinguish general conversation from actionable requests.

### 3. Classify every comment

Group feedback into categories such as correctness, security, performance, maintainability, tests, documentation, and style. Mark comments as actionable, informational, duplicate, conflicting, or needing clarification.

### 4. Build an implementation plan

For every actionable thread, record the file, requested behavior, expected outcome, dependencies, and verification method. Ask for clarification when a comment is ambiguous or conflicts with project requirements.

### 5. Get approval where needed

When many changes are requested or a comment may alter behavior beyond the review's scope, present the plan before implementing. Do not silently expand the requested work.

### 6. Apply focused fixes

Make the smallest correct change that addresses the reviewer's concern. Avoid unrelated refactoring and preserve established project conventions.

### 7. Test and inspect

Run the relevant automated tests, lint checks, type checks, and build steps. Inspect the final diff to ensure each change corresponds to a review request and no unintended files were modified.

### 8. Respond to each thread

Reply with the specific change made, relevant test result, or a reasoned explanation. Do not claim a fix is complete before it has been verified.

### 9. Resolve and verify threads

Resolve a thread only after the requested concern is addressed and the reply is accurate. Leave unresolved or disputed items open and document the reason.

### 10. Summarize completion

Provide a final summary with addressed threads, tests run, outstanding questions, and any items that require reviewer confirmation.

## Comment Tracking Status

| Status | Meaning |
|---|---|
| Pending | Not yet reviewed |
| Understood | Intent and expected behavior are clear |
| In progress | Implementation is underway |
| Addressed | Change or explanation is complete |
| Needs clarification | Request is ambiguous or conflicting |
| Not applicable | Reason is documented and communicated |
| Verified | Fix and response have been checked |

## Included Resources

- [Review comment tracker](resources/review-comment-tracker.md)
- [Reviewer response templates](resources/reviewer-response-templates.md)

## Quality Checklist

- Every review thread has been inspected.
- Duplicate comments are grouped without losing thread context.
- Ambiguous requests are clarified before implementation.
- Changes match the reviewer's intent.
- Unrelated files are not modified.
- Tests are run and their results are reported accurately.
- The final diff is reviewed.
- Replies are specific, factual, and respectful.
- Threads are resolved only when the underlying concern is addressed.
- Outstanding disagreements remain visible.

## Important Notes

A posted reply is not proof that a review comment has been addressed. Verify the code, tests, documentation, or decision that resolves the concern. Do not force-resolve a thread simply to make the pull request appear complete.

## Repository Structure

~~~text
claude-address-github-comments-skill/
├── SKILL.md
├── README.md
├── LICENSE
└── resources/
    ├── review-comment-tracker.md
    └── reviewer-response-templates.md
~~~

## License

Released under the MIT License. Copyright (c) 2026 Brajesh Kumar. See the root `LICENSE` file for the complete terms.
