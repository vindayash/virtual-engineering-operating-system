# Dependency Management

Dependencies extend application capability.

They also introduce responsibility.

Every dependency becomes part of the system.

---

# Dependency Philosophy

A dependency should provide clear value.

Adding code is easy.

Maintaining code is the responsibility.

---

# Existing Project Rule

Existing dependency strategy has priority.

Before changing:

Understand:

* package choices
* versions
* compatibility requirements
* deployment constraints

Do not replace dependencies unnecessarily.

---

# Before Adding Dependencies

Ask:

Is this problem already solved?

Can existing tools handle it?

Is the dependency worth maintaining?

Do not install packages automatically.

---

# Dependency Cost

Every dependency adds:

* security responsibility
* updates
* compatibility risks
* maintenance

Small packages still create ownership.

---

# Use Trusted Packages

Prefer dependencies that are:

* maintained
* documented
* widely reviewed
* stable

Avoid abandoned packages.

---

# Avoid Dependency Bloat

Do not add libraries for:

* tiny utilities
* simple functions
* unnecessary convenience

Sometimes writing simple code is better.

---

# Version Control

Pin dependencies when required.

Avoid unexpected production changes.

Example:

Unexpected package update

↓

Application failure

---

# Lock Files

Respect lock files.

Examples:

requirements lock files

package lock files

They protect reproducible builds.

---

# Updating Dependencies

Update intentionally.

Review:

* breaking changes
* security fixes
* compatibility

Do not blindly upgrade everything.

---

# Security Updates

Security updates have priority.

Evaluate:

* vulnerability impact
* affected systems
* required action

---

# Removing Dependencies

Remove packages that are:

* unused
* replaced
* unnecessary

Unused dependencies still create risk.

---

# Framework Dependencies

Do not install libraries that duplicate framework features.

Example:

Framework already provides authentication support.

Understand before adding alternatives.

---

# Small Libraries

Be careful with packages that solve very small problems.

A few lines of maintainable code may be safer.

---

# Large Libraries

Large dependencies require:

* learning cost
* upgrade planning
* architecture impact

Add intentionally.

---

# External Services

Third-party services are dependencies too.

Consider:

* reliability
* cost
* limits
* failure behavior

---

# Dependency Isolation

Avoid spreading dependency-specific code everywhere.

Encapsulate when useful.

This makes replacement easier.

---

# Generated Dependencies

Review generated project dependencies.

Templates often include unnecessary packages.

Remove unused ones.

---

# Licensing

Consider license requirements.

Some projects have restrictions.

---

# Production Impact

Before adding:

Understand impact on:

* build size
* startup time
* performance
* deployment

---

# Documentation

Document unusual dependency choices.

Explain why the dependency exists.

---

# Warning Signs

Review dependencies when:

* nobody knows why package exists
* simple features require many packages
* updates constantly break systems
* security warnings are ignored

---

# Dependency Checklist

Before adding:

[ ] Existing solution checked

[ ] Package maintained

[ ] Security considered

[ ] Long-term ownership accepted

[ ] Complexity justified

---

# Final Principle

A dependency is borrowed code.

Borrow carefully because maintaining it becomes your responsibility.