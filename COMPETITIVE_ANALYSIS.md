# Competitive Analysis: SPECify

*Last updated: August 15, 2026*

## Market Overview

The "code understanding" space exploded in 2025-2026, driven by AI coding agents needing better context about codebases. Multiple tools now generate diagrams, analyze dependencies, or provide AI-powered code explanations. However, **no tool connects understanding → agent-ready handoff** in a single flow.

## Direct Competitors

### 1. oh-my-mermaid (ohmymermaid.com)
- **What it does:** Claude Code skills (/omm-scan, /omm-push) that generate Mermaid architecture diagrams from codebases. View locally or push to cloud.
- **Stars:** Growing quickly (2025-2026)
- **Strengths:** Beautiful output, drillable diagrams, git-committed, AI-generated
- **Weaknesses:** Locked to Claude Code only, no "focus mode", no agent prompt generation, no PR review, just diagrams
- **Gap we fill:** LLM-agnostic, focus mode, agent-ready prompts, relationship analysis

### 2. codeindex (codeindex.cc)
- **What it does:** Tree-sitter powered CLI that extracts symbols and dependencies. Blast-radius impact scoring. Outputs README_AI.md navigation files.
- **Stars:** ~500+ (growing)
- **Strengths:** Fast (tree-sitter), multi-language, blast-radius scoring, AI-agent friendly output
- **Weaknesses:** No diagrams, no doc consolidation, no LLM-powered analysis, no interactive focus mode
- **Gap we fill:** Visual output (Mermaid), LLM-powered understanding, interactive focus mode, prompt generation

### 3. opencodehub (github.com/theagenticguy/opencodehub)
- **What it does:** Graph-based impact analysis over MCP. Pre-computed clustering, execution-flow tracing, blast-radius analysis.
- **Strengths:** MCP integration, pre-computed graphs (fast at query time), open source (Apache-2.0)
- **Weaknesses:** MCP-only access, no standalone CLI, no diagrams, no doc consolidation
- **Gap we fill:** Standalone CLI, visual diagrams, doc consolidation, broader scope

### 4. CodePulse AI (github.com/codedbyasim/codepulse-ai)
- **What it does:** GitHub repo analyzer using Gemini. Generates docs, architecture diagrams, security assessments, refactoring recommendations.
- **Strengths:** Comprehensive analysis, nice output
- **Weaknesses:** Locked to Google Gemini, no focus mode, no agent handoff, no PR review integration
- **Gap we fill:** LLM-agnostic, focus mode, agent prompts, PR review

### 5. Greptile (greptile.com)
- **What it does:** SaaS AI code review platform. Memory + MCP integration. $30/seat/month. Analyzes full codebase context for PR reviews.
- **Strengths:** Deep codebase understanding, production-ready, enterprise features, memory across reviews
- **Weaknesses:** Expensive ($30/dev/month), SaaS-only (no self-host), focused on PR review only, not general understanding
- **Gap we fill:** Free, open source, broader scope (not just reviews), self-hostable, focus mode

### 6. Skylos (github.com/duriantaco/skylos)
- **What it does:** Open-source static analysis CLI. Finds dead code, security bugs, secrets, quality regressions. 12 languages.
- **Strengths:** Multi-language, fast, PR scanner, CI/CD friendly
- **Weaknesses:** Pure static analysis — no AI understanding, no diagrams, no context generation
- **Gap we fill:** AI-powered understanding, visual diagrams, agent-ready output

### 7. iago (github.com/drakulavich/iago)
- **What it does:** Mermaid diagrams for AI code reviews. Claude Code skill, run /iago after /review.
- **Strengths:** Clean diagrams, integrates with review flow
- **Weaknesses:** Review-only (not general understanding), Claude Code only, single-purpose
- **Gap we fill:** Full repo understanding, any LLM, focus mode, broader scope

### 8. codespaces/diskd-ai (github.com/diskd-ai/codespaces)
- **What it does:** Agent skill that builds a queryable "belief map" of a codebase. Architecture discovery, blast-radius analysis, boundary checks.
- **Strengths:** Belief map concept is powerful, boundary violation checks
- **Weaknesses:** Agent skill only (not standalone), Python/TypeScript only, no visual output
- **Gap we fill:** Standalone tool, visual diagrams, focus mode, any language

## Indirect Competitors

| Tool | What It Does | Key Difference |
|------|-------------|---------------|
| GitHub Copilot (explain) | Ad-hoc code explanation | No persistent output, no diagrams |
| Cursor chat | Ask questions about codebase | Ephemeral, no structured output |
| Augment Code | Enterprise codebase understanding | Very expensive, enterprise only |
| Sourcegraph | Code search + navigation | Not AI-powered analysis, search-focused |

## The Unique Angle: Focus Mode + Agent Handoff

**What nobody does well:**

```
"I need to modify this class to add OAuth support"
     ↓
Show me: related files, dependencies, data flow, test coverage
     ↓
Generate: A complete, structured prompt I can hand to any agent
```

This "understand → act" bridge is the killer feature. Most tools stop at understanding.

## Competitive Moat

| Factor | Our Advantage |
|--------|--------------|
| **Focus mode** | Nobody does "zoom into a piece, show relationships, generate prompt" |
| **Agent handoff** | Understanding → actionable prompt is a unique flow |
| **LLM-agnostic** | Works with any provider (not locked to Claude/Gemini) |
| **Combined scope** | Diagrams + docs + focus + prompts in one tool |
| **Open source CLI** | Not a $30/mo SaaS |
| **Offline capable** | Works with local LLMs via Ollama |

## Risk Assessment

| Risk | Likelihood | Mitigation |
|------|-----------|-----------|
| oh-my-mermaid adds focus mode | Medium | Ship first, broader scope |
| LLMs get better at ad-hoc codebase explanation | High | Structured, persistent output is still valuable |
| Tree-sitter complexity for multi-language | Medium | Start with TS/Python/Go, expand |
| codeindex adds diagrams | Low | Our differentiator is the full flow, not just one feature |

## Verdict

**Competition level: 🟡 MEDIUM**

The space is crowded with partial solutions, but nobody has nailed the full loop: Analyze → Visualize → Focus → Generate Agent Prompt. The "focus mode + agent handoff" angle is genuinely underserved. Main risk is that the space is moving fast and bigger players (Greptile, oh-my-mermaid) could add these features.

---

*Content was rephrased for compliance with licensing restrictions. Sources linked inline.*
