# Agent Instructions

This repository contains agent-evaluation tasks. Read the relevant task file before acting, keep changes focused, and avoid destructive or system-level actions without explicit approval.

## Local Environment and Setup

- Device: MacBook Air, Apple M4 (arm64), 24 GB RAM, ~74 GB free disk
- OS: macOS 27.2 (Darwin 27.2.0); shell: zsh
- Always use arm64/Apple Silicon builds (`darwin-arm64` / `aarch64-apple-darwin`), not x86_64

### Tooling

- Installed: Homebrew 7.0.14 (`/opt/homebrew`), git 2.39.5, Node 24.4.1 + npm 11.4.2, uv 0.8.0, Xcode CLT (`/Library/Developer/CommandLineTools`)
- Python 3.13.5 via venv `~/Development/envs/ml_env_1` (the active `python3`/`pip3`); for new projects, create a separate venv with `uv venv`
- Not installed: docker, go, rust/cargo, gh, pnpm, conda, a working Java runtime (`/usr/bin/java` is a stub)
- System ruby is 2.6 (outdated); don't rely on it

### Conventions

- Prefer `brew install` (formulae first, `--cask` for GUI apps) over manual downloads/.dmg
- Projects live in `~/Development`
- `sudo` needs an interactive password, so avoid it and prefer user-level installs

### Important Restrictions

- Don't do iireversible changes/ deletions etc that may destroy data
- However, if you're replacing a file/ changing a file etc, that's not considered irreversible
- This is especially the case for files residing outside of the project root directory
- This also means system-level changes must be done with care, especially if they are increasingly outside the scope of a given task

---

## Project Workflow Instructions

This section is only intended for executing non-trivial tasks/project-style work, which includes working over some code for some period of time. Use your judgment about creating these documents in the workflow.

We will work together on designing and implementing various software modules, projects, and tasks for them.

I have the following simplified workflow for that. The idea is to maintain a document for each stage so that all of that serves as complete documentation for the project. Both humans and agents can then use them as reference points as the project progresses. Those documents can then be updated as needed.

The documents may be updated throughout the stages and progression of the project. They don't have to be sequential. For example, the design may be updated with lessons learned during implementation, so stages 2 and 3 may be a loop. Once some implementation and testing has been done, a README file can be created. As the project progresses and implementation changes, this README will also need to be updated. 

It is important that the documents are not overly verbose. They need to be concise and clear and to the point, for the benefit of both humans and agents. 

Use these workflow instructions as a guideline rather than absolute rules. 

1. Brainstorming 
- Document: BRAINSTORMING.md
- Open brainstorming and discussion starting from a basic idea
- Exploring multiple branches of an idea tree and refining the ideas, etc.
- We will try to narrow down on a final refined idea/approach for design and implementation 
- For simple tasks, tools, etc., we will skip the brainstorming and directly go to the Stage 2: Design stage

2. Design stage
- Document: DESIGN.md
- Capture the high-level design, architecture, and key decisions and features for the purpose of architecting a solution based on the final refined idea 
- It will be used as the central reference point for many tasks, including understanding the system (both humans and agents), as for implementation agents and testing agents, etc.
- So you can include diagrams etc - aim for structural clarity and a clear understanding of the system architecture.

- 3. Implementation stage
- Document: IMPLEMENTATION.md
- Capture the detailed implementation steps, code structure, and any important decisions made during the implementation phase.
- Testing will also be coverd in this document, including the test coverage etc.
- Include any lessons learned during the implementation and testing phases, so that future work can benefit from these insights.
- This may also include things like commands/ scripts to run for building, testing, or deploying and other such tasks.
- This document will serve as a reference for understanding the actual implementation and for future maintenance or enhancements.

4. Documentation
- Document: README.md
- This document is aimed primarily for humans, but agents will also be using this. 
- It should have a very brief overview section - describing its purpose, key features etc
- It should then have a section for instructions for usage, including commands for running (first), then building, testing etc. - commands in copyable snippets.
- Aim for brevity, just like the front page, README of a GitHub project. 

---

## Coding Style

- Prefer simple and readable code over complex and clever solutions.
- Follow consistent naming conventions for variables, functions, classes, and modules.
- Write modular and reusable code wherever possible. But don't over-engineer, over-abstract or introduce unnecessary complexity.
- Don't try to cover every possible edge case or scenario; focus on the most important and likely ones.
- Similarly, error handling is needed only for standard, idiomatic cases and not for every possible edge case.
- Commenting: minimal and as needed, focusing on non-obvious code sections. In-line where appropriate.