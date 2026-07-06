# Dependency Security

Third-party dependencies become part of the application.

Their security becomes your responsibility.

---

# Dependency Security Philosophy

A dependency is trusted external code.

Before adding it:

Understand the value.

Understand the risk.

---

# Existing Project Rule

Existing dependency choices have priority.

Before replacing:

Understand:

* why dependency exists
* where it is used
* compatibility requirements

Do not remove or replace packages blindly.

---

# Dependency Ownership

Adding a dependency means accepting:

* updates
* vulnerabilities
* breaking changes
* maintenance

Free code is not free responsibility.

---

# Before Adding Dependencies

Ask:

Do we need this?

Is it maintained?

Is it secure?

Does existing code solve this?

Avoid unnecessary additions.

---

# Trusted Sources

Use packages from trusted ecosystems.

Review:

* maintainers
* activity
* documentation
* community usage

---

# Abandoned Packages

Avoid packages with:

* no maintenance
* unresolved security issues
* unclear ownership

Unmaintained code creates risk.

---

# Small Dependencies

Be careful adding packages for tiny features.

A few lines of simple code may be safer.

---

# Large Dependencies

Large frameworks or libraries require:

* security awareness
* upgrade planning
* deeper understanding

Adopt intentionally.

---

# Version Management

Control dependency versions.

Unexpected updates can introduce:

* bugs
* vulnerabilities
* breaking changes

---

# Lock Files

Respect dependency lock files.

They provide:

* repeatable builds
* predictable deployments

---

# Vulnerability Scanning

Use security scanning when possible.

Check:

* known vulnerabilities
* outdated packages
* risky versions

---

# Security Updates

Prioritize important security fixes.

Before updating:

Understand:

* impact
* compatibility
* required changes

---

# Transitive Dependencies

Dependencies bring other dependencies.

Review dependency trees when needed.

Indirect code still runs in your system.

---

# Removing Dependencies

Remove:

* unused packages
* replaced libraries
* unnecessary tools

Less code means less attack surface.

---

# Supply Chain Risk

Be careful with:

* unknown packages
* sudden ownership changes
* suspicious updates

Package sources matter.

---

# Production Dependencies

Separate:

runtime dependencies

from

development dependencies

Production should contain only what it needs.

---

# Dependency Permissions

Some dependencies request access.

Examples:

* filesystem
* network
* environment

Understand why.

---

# External Services

External APIs are dependencies too.

Consider:

* availability
* security
* data exposure

---

# Generated Projects

Review generated dependency lists.

Templates often include packages never used.

---

# AI Generated Code Rule

Generated code should not automatically add dependencies.

Prefer existing project tools.

Add packages only with clear benefit.

---

# Warning Signs

Review dependencies when:

* nobody knows why a package exists
* updates are avoided forever
* vulnerability warnings ignored
* simple tasks need many libraries

---

# Dependency Security Checklist

Before completion:

[ ] Dependency is necessary

[ ] Source is trusted

[ ] Maintenance checked

[ ] Versions controlled

[ ] Security impact considered

---

# Final Principle

Every dependency is code you choose to trust.

Choose carefully.