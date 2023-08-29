## Title

Standard Release Process

## Patlet

Teams may hesitate to adopt an InnerSource project if they are unsure of its maturity. To address this, consistent release notes and published artifacts are crucial. These practices showcase a strong dedication to the project, instilling confidence and assuring users of ongoing commitment to sustainable and well-managed software.

## Problem

When a team is deciding whether to use an InnerSource project, one of their considerations is whether they can rely on the given project for an extended period. Switching the tools/projects that they are using has a cost, so they only want to make those investments when necessary and has tangible benefits.

It is common practice for Open Source projects to have versioned releases, with notes documenting breaking changes, and new features along with either a published binary or link to a Docker image. This practice may not be as transparent or well documented/visible for InnerSource projects, modules, etc.

InnerSource projects that don't have a published artifact or release process reduces trust. Teams won't know when they can expect the next release, when breaking changes are introduced, etc.

## Context

Large organizations produce a lot of internal software, much of which could be reused by teams across the company. Operational tooling, software libraries, and infrastructure as code (IaC) modules are common examples of this type of software. Most large organizations, however, don't publish internal software to be consumed by other teams in the company. This can occur either because they are to busy to provide documentation or don't realize the projects value to others.

An internal or public source repository should be available where source code is stored, but teams lack a process for making software consumable by outside teams.

As an organization grows and more internal software is written, the value of this pattern grows.

## Forces

### Difficult for organizations that don't have a central CI/CD system

For organizations that don't provide engineers a centralized CI/CD system, automating a build and release process can be challenging. The team may need to stand up their own tool (Jenkins, Drone, etc). Without a CI/CD system, builds and release notes can still be produced, however, it may require a local build of the software and manual upload to whichever tool is hosting build artifacts.

### Added burden of publishing release notes

In addition to building your source code, writing release notes can be tedious without the ability to auto-generate a list of git commits. This would be left for someone to do manually, in addition to writing more high level details on a release.

### Increased difficulty without a location to host artifacts

If a company does not provide a centralized location for storing build artifacts (jars, npm modules, etc.) and docker images, engineers may be left deciding for themselves where is appropriate to store versioned software. Tools like GitHub provide this for you, however, if a company is not using one of these popular tools, this could pose a burden.

## Solution

By providing clear **release notes** and a published artifact you increase people's confidence that you are publishing a quality product that they can rely on.

The following are key elements to achieve this:

- A CI/CD pipeline is located within your repository that [automates the release process](https://opensource.guide/best-practices/#use-tools-to-automate-basic-maintenance-tasks)
- Build artifacts are generated by the CI/CD system (binary, docker image, jar, etc)
- Releases are clearly labeled and tagged with [semantic versioning](https://github.com/semantic-release/semantic-release)
- Releases include notes on New Features, Bug Fixes, and any "Breaking Changes"

A good example of quality release notes can be found [here](https://github.com/jaegertracing/jaeger/releases).

## Resulting Context

Teams who come across your project will see published release notes and gain confidence in your tool. Published artifacts also make using your product easier and quicker to adopt. Having well-defined and visible processes such as these also help with cross-team collaboration and new contributors. Folks can be confident that their contributions are made available and distributed in a reasonable amount of time with a clear usage path.

Release notes are also a great opportunity to [praise participants](praise-participants.md)! As we know, [documentation is extremely important](project-setup/base-documentation.md) for new folks looking to get involved with your project. Praising outside teammates for contributions, including documentation and release notes, is a great way to foster community and grow your user base.

## Known Instances

* Comcast (multiple projects)
* GitHub (multiple projects)

## Authors

David Grizzanti

## Status

Structured