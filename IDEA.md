# SPECify — Codebase Intelligence & Agent Handoff Tool

## Concept

A CLI tool that analyzes codebases to generate structured documentation, visual diagrams, and agent-ready prompts. It bridges the gap between "understanding code" and "having an AI agent make changes to it correctly."

## Core Features

### Mode 1: Analyze (Full Repo)
- Discover existing documentation and code comments
- Map module dependencies and architecture
- Generate Mermaid diagrams (call flow, module deps, data flow)
- Consolidate scattered docs into structured markdown
- Identify testing gaps and tech debt indicators

### Mode 2: Focus (Zoom Into a Piece)
- Point at a file, class, or function
- Map all relationships (imports, consumers, data flow)
- Show blast radius of potential changes
- Optionally specify a goal: "I need to add OAuth here"
- Generate a complete agent-ready prompt with full context

### Mode 3: Review (PR Analysis)
- Analyze one or more PRs in context of the repo
- Show what's affected, what might break
- Generate structured review notes
- Multi-PR correlation (related changes across PRs)

## Example Usage

```bash
# Install
npm install -g specify

# Full repo analysis
specify analyze ./my-repo

# Focus on a specific area
specify focus ./src/auth/login.ts
specify focus ./src/auth/ --goal "add OAuth2 support"

# Review PRs
specify review PR#123 PR#456 --depth deep

# Output
.specify/
  architecture.md
  diagrams/
    module-deps.mmd
    call-flow.mmd
    data-flow.mmd
  focus/
    auth-login.md
    auth-login.prompt.md    ← agent-ready prompt
  reviews/
    pr-123.md
```

## Tech Stack

- TypeScript + Node.js (Bun for speed)
- CLI: Commander.js
- AST Parsing: tree-sitter (multi-language)
- Diagrams: Mermaid.js output
- LLM: Provider abstraction (OpenAI/Anthropic/Ollama)
- Config: cosmiconfig (.specifyrc pattern)
- Git/GitHub: simple-git + octokit for PR analysis

## Key Differentiators

1. **Focus Mode** — Nobody does "zoom in, show relationships, generate agent prompt" well
2. **Agent Handoff** — Outputs aren't just for humans; they're structured for AI agents
3. **LLM Agnostic** — Not locked to one AI provider
4. **Combined Scope** — Diagrams + docs + focus + review in one tool
5. **Local/Offline** — Works with Ollama, no cloud dependency

## Target Users

- Developers joining a new codebase
- Tech leads reviewing architecture
- Anyone preparing context for AI coding agents
- Teams doing code reviews across multiple PRs

## Status

📋 **Idea** — Not yet implemented
