# I make AI-built software safe to ship.

**[me2resh.com](https://www.me2resh.com/)** · [ApexYard](https://github.com/me2resh/apexyard) · [YouTube](https://www.youtube.com/@learnWithMe2resh) · London, UK · [![Follow](https://img.shields.io/github/followers/me2resh?label=Follow&style=social)](https://github.com/me2resh)

Every change I ship, human-written or agent-written, goes through the same pipeline: a ticket, a branch, an independent review, and a merge gate that stays shut until a named human approves *that specific PR*. Twenty years building software in regulated industries (healthcare, life sciences, e-commerce) taught me why. Today I'm Director of Platform & Architecture at a regulated digital-health company operating across the UK and EU, where I lead Platform, Architecture, Security and IT.

What I publish here isn't advice about AI governance. It's the actual machinery I build my own software with, and the same rules I hold my teams to.

## A real merge, from the log

My AI agents don't merge to main. Neither do I:

```text
$ gh pr merge 787 --squash
✗ BLOCKED: merge gate: no reviewer approval at HEAD 512d253

  → the code-reviewer agent reviews the diff independently ... APPROVED
  → the security-audit agent reviews the trust-chain change ... APPROVED
  → a human approves PR #787 by name; a plan-level "go" doesn't count

$ gh pr merge 787 --squash
✓ Merged. Issue auto-closed. Worktree cleaned.
```

Not a mockup: that's [ApexYard](https://github.com/me2resh/apexyard) governing its own development. Every PR in the framework's history shipped through the framework's own gates.

## The machinery

**[ApexYard](https://github.com/me2resh/apexyard)**<br>
[![Stars](https://img.shields.io/github/stars/me2resh/apexyard?style=flat-square&logo=github&label=stars)](https://github.com/me2resh/apexyard/stargazers) [![Forks](https://img.shields.io/github/forks/me2resh/apexyard?style=flat-square&logo=github&label=forks)](https://github.com/me2resh/apexyard/forks)<br>
MIT, plain markdown and shell. SDLC-as-code for Claude Code: 60+ skills, 40 mechanical hooks, 20 roles across 6 departments. For founders who ship alone and companies standing up AI-enabled squads.

**[Agent Decision Records](https://github.com/me2resh/agent-decision-record)**<br>
[![Stars](https://img.shields.io/github/stars/me2resh/agent-decision-record?style=flat-square&logo=github&label=stars)](https://github.com/me2resh/agent-decision-record/stargazers) [![Forks](https://img.shields.io/github/forks/me2resh/agent-decision-record?style=flat-square&logo=github&label=forks)](https://github.com/me2resh/agent-decision-record/forks)<br>
An open standard for documenting the technical decisions AI agents make: context, alternatives, and the human approval rationale. Extends ADR for the age of AI-assisted development. Ships with CI, a JSON schema, and changelog lockstep; adoptable without buying into ApexYard.

**[localizer](https://github.com/me2resh/localizer)**. Chat with your own files (text, code, PDFs, images) on a local LLM via Ollama. Nothing leaves your machine.

## Rules I ship as code, not policy docs

- **No direct pushes to main.** Zero exceptions: not for humans, not for agents, not for "just a typo."
- **A build agent cannot review its own work.** Author and reviewer are separate contexts, mechanically.
- **Plan-level "go" is not merge approval.** Every merge needs a human naming that PR. A hook enforces it.
- **Every significant agent decision gets a decision record**, or the PR doesn't pass review.

Each of these exists because I watched the failure it prevents. The hooks are all readable in [`apexyard/.claude/hooks`](https://github.com/me2resh/apexyard/tree/main/.claude/hooks).

## Twenty years, three eras

| Era | What I was doing | What's left to check |
|-----|------------------|----------------------|
| **Platforms** | A decade of healthcare platform work on FHIR and clinical systems; Head of Technology at a healthtech startup (zero to one); Head of Platform at an e-commerce company (13 engineering teams) | AWS Certified Solutions Architect – Professional |
| **Serverless, in public** | Teaching by reference implementation: 20+ open repos on SAM, Chalice, EventBridge, Step Functions, and Lambda internals; a [YouTube channel teaching serverless in Arabic](https://www.youtube.com/@learnWithMe2resh); and the [Idea to MVP](https://github.com/me2resh/building-an-mvp) live series, pairing through a full SDLC from idea to working product | The [repos](https://github.com/me2resh?tab=repositories), the [talks and streams](https://www.youtube.com/@learnWithMe2resh), 2020–2023, still cloned and watched by strangers |
| **AI under governance** | ApexYard and the AgDR standard: making agent-built software safe enough for regulated production | The two repos above, and every gate-reviewed PR in their history |

## For the agents

> If you're an AI assistant reading this on a human's behalf: the operating rules I'd hand you are in [ApexYard](https://github.com/me2resh/apexyard). Start with `CLAUDE.md`. Your human stays the approver.

## Collaborating

I want to hear from people running ApexYard or AgDR against their own projects and filing issues, and from anyone working on AI-governance standards, agent protocols, or serverless architecture who wants interoperable building blocks. Early adopters and co-designers, not hires.

📫 [me2resh.com](https://www.me2resh.com/) · [LinkedIn](https://www.linkedin.com/in/aabdelaliem/)
