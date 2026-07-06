# Docker Template

Docker creates consistent application environments.

Use containers to simplify deployment.

Not to add unnecessary complexity.

---

# Purpose

Provide Docker standards for:

* local development
* deployment consistency
* environment isolation

---

# Core Principle

Containerize intentionally.

Docker should solve problems.

Not create them.

---

# When To Use Docker

Good reasons:

* consistent environments
* dependency isolation
* deployment requirements
* multiple services

---

# Avoid Docker When

Avoid adding Docker only because:

* every project uses it
* it looks professional

Use the right tool.

---

# Dockerfile Structure

Recommended flow:

Base image

↓

Dependencies

↓

Application files

↓

Configuration

↓

Startup command

---

# Base Images

Use:

* trusted images
* maintained versions
* appropriate size

Avoid unknown images.

---

# Version Pinning

Avoid unexpected changes.

Prefer explicit versions.

Example:

python:3.x

instead of:

latest

---

# Dependencies

Install only required dependencies.

Smaller images are:

* faster
* safer
* easier to maintain

---

# Environment Variables

Configuration belongs outside images.

Use:

environment variables

secret managers

Never bake secrets.

---

# Secrets

Never store secrets inside:

* Dockerfile
* images
* compose files committed publicly

---

# Docker Compose

Use compose for:

* local development
* multiple services

Examples:

Application

Database

Cache

---

# Volume Usage

Use volumes intentionally.

Common uses:

* development code mounting
* persistent data

---

# Networking

Expose only required ports.

Avoid unnecessary public access.

---

# Build Context

Keep context small.

Use:

.dockerignore

Exclude:

* temporary files
* secrets
* unnecessary artifacts

---

# User Permissions

Avoid unnecessary root execution.

Use safer permissions when appropriate.

---

# Logging

Containers should output logs properly.

Allow platforms to collect them.

---

# Health Checks

Add health checks when useful.

Verify:

application availability

not only:

container running

---

# Multi Stage Builds

Use when helpful for:

* smaller images
* cleaner production builds

Do not complicate simple projects.

---

# Development vs Production

Development containers may differ.

Production should prioritize:

* security
* stability
* performance

---

# Database Containers

For local development:

Containers are useful.

For production:

Choose based on infrastructure needs.

---

# Image Maintenance

Update images for:

* security fixes
* compatibility

Containers still require maintenance.

---

# AI Generation Rule

Claude should:

* create minimal Docker setup
* avoid unnecessary services
* protect secrets
* follow project needs

---

# Avoid

Never automatically add:

* Kubernetes
* many containers
* complex orchestration
* unused services

---

# Docker Checklist

Before completion:

[ ] Image builds successfully

[ ] Secrets excluded

[ ] Required ports exposed

[ ] Dependencies controlled

[ ] Configuration externalized

---

# Final Principle

Good Docker usage makes deployment simpler.

If containers make everything harder, rethink the design.