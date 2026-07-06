# Git Workflow

Git records the history of software changes.

A good history helps teams understand how a system evolved.

---

# Git Philosophy

Version control should provide:

* traceability
* collaboration
* recovery
* understanding

Commits tell the story of a project.

---

# Existing Project Rule

Existing Git workflow has priority.

Before changing:

Understand:

* branching strategy
* commit style
* release process
* team workflow

Do not replace workflows unnecessarily.

---

# Commit Purpose

A commit should represent one meaningful change.

Good:

Add user authentication

Fix invoice calculation issue

Bad:

Updated stuff

Changes

Final fix

---

# Commit Size

Prefer smaller focused commits.

Avoid:

one huge commit containing:

* features
* refactoring
* formatting
* unrelated fixes

---

# Commit Messages

Messages should explain intent.

Recommended:

Action + purpose

Examples:

Add payment validation

Fix expired token handling

Improve report query performance

---

# Branches

Use branches to isolate work.

Examples:

feature/user-profile

fix/login-error

Follow project conventions.

---

# Main Branch

Main production branches should remain stable.

Avoid committing experimental changes directly.

---

# Pull Requests

Pull requests should be:

* focused
* reviewable
* understandable

Smaller PRs get better reviews.

---

# Pull Request Description

Include when useful:

* what changed
* why it changed
* testing notes
* risks

Help reviewers.

---

# Avoid Mixing Changes

Separate:

Feature work

Refactoring

Formatting

Bug fixes

when possible.

Mixed changes are harder to review.

---

# Code Formatting Changes

Large formatting changes should be separate.

Avoid hiding functional changes inside formatting.

---

# Merge Conflicts

Resolve conflicts carefully.

Understand both changes.

Do not blindly accept one side.

---

# Force Push

Use force push carefully.

Avoid rewriting shared history unexpectedly.

---

# Secrets

Never commit:

* passwords
* tokens
* private keys
* credentials

Remove immediately if exposed.

---

# Generated Files

Understand before committing generated files.

Some belong in Git.

Some do not.

Follow project rules.

---

# Dependencies

Dependency changes should be intentional.

Avoid accidental lock file updates.

---

# Releases

Production releases should identify:

* version
* commit
* changes

Know what is running.

---

# Tags

Use tags when helpful for:

* releases
* deployments
* important versions

---

# Git Ignore

Maintain proper ignore rules.

Exclude:

* local files
* temporary files
* secrets
* generated artifacts when appropriate

---

# Reverting

Prefer safe reversions.

Understand what change caused the issue.

---

# Large Files

Avoid storing large unnecessary files.

Use appropriate storage solutions.

---

# Warning Signs

Review Git workflow when:

* nobody understands history
* commits contain unrelated changes
* secrets appear in repository
* reviews become impossible

---

# Git Checklist

Before pushing:

[ ] Change is focused

[ ] Commit message is meaningful

[ ] Secrets removed

[ ] Tests considered

[ ] Unrelated changes excluded

---

# Final Principle

Git history is documentation.

Write history that helps future engineers.