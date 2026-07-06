# Python Dependency Management

Dependencies are external code that become part of your system.

Every dependency adds responsibility.

Use dependencies intentionally.

---

# Dependency Philosophy

A dependency should:

* solve a real problem
* reduce complexity
* improve maintainability

Dependencies are not free.

Every package introduces:

* security responsibility
* updates
* compatibility risks
* maintenance overhead

---

# Existing Project Rule

Existing dependency management has priority.

When modifying projects:

Respect existing tools:

* requirements.txt
* pip
* poetry
* pipenv
* uv

Do not migrate dependency systems without reason.

---

# Before Adding A Dependency

Ask:

1. Is this problem already solved?

2. Does the standard library handle it?

3. Is the package maintained?

4. Is the package secure?

5. Is the added complexity worth it?

If not:

Do not add it.

---

# Avoid Dependency Driven Development

Do not search for a package before understanding the problem.

Bad:

Need small helper function

↓

Install package

Good:

Understand problem

↓

Evaluate options

↓

Choose simplest solution

---

# Standard Library First

Prefer Python standard library when practical.

Examples:

* pathlib
* datetime
* json
* logging
* collections

Avoid installing packages for simple built-in capabilities.

---

# Package Selection

Choose packages based on:

* maintenance activity
* community usage
* documentation quality
* security history
* compatibility

Popularity alone is not enough.

---

# Version Management

Pin versions appropriately.

Avoid uncontrolled updates.

Bad:

package

Better:

package==x.x.x

or controlled version ranges.

Reproducible environments matter.

---

# Dependency Updates

Update intentionally.

Consider:

* security fixes
* breaking changes
* compatibility
* testing requirements

Do not blindly upgrade production dependencies.

---

# Security

Regularly check dependencies for:

* vulnerabilities
* abandoned packages
* unsafe behavior

Dependency security is application security.

---

# Removing Dependencies

Remove packages when:

* no longer used
* replaced by simpler solutions
* security risk is high

Unused dependencies still create risk.

---

# Development Dependencies

Separate application dependencies from development tools.

Examples:

Runtime:

* web frameworks
* database drivers

Development:

* testing tools
* formatters
* linters

Production should contain only what it needs.

---

# Virtual Environments

Use isolated environments.

Avoid installing project dependencies globally.

Each project owns its environment.

---

# Lock Files

Use lock files when supported.

They provide:

* reproducible builds
* predictable deployments
* safer updates

Production should be repeatable.

---

# Dependency Size

Consider dependency weight.

A small feature should not require a large dependency tree without reason.

More packages mean more ownership.

---

# Framework Dependencies

Respect framework ecosystems.

Do not replace built-in framework solutions unnecessarily.

Example:

Avoid adding a library when the framework already provides a reliable feature.

---

# Internal Packages

Create internal packages only when:

* reuse exists
* ownership is clear
* maintenance is planned

Do not create shared packages for imaginary reuse.

---

# Dependency Review Checklist

Before adding:

[ ] Problem is understood

[ ] Standard library checked

[ ] Package is maintained

[ ] Security considered

[ ] Maintenance cost accepted

[ ] Existing project style respected

---

# Warning Signs

Review dependencies when:

* nobody knows why a package exists
* dependency list grows constantly
* updates become impossible
* security alerts are ignored
* simple tasks require many packages

---

# Final Principle

The best dependency is the one you do not need.

The second best dependency is one chosen carefully and maintained responsibly.