# My AI agents don't merge to main. Neither do I.

**[me2resh.com](https://www.me2resh.com/)** · [ApexYard](https://github.com/me2resh/apexyard) · London, UK · [![Follow](https://img.shields.io/github/followers/me2resh?label=Follow&style=social)](https://github.com/me2resh)

Every change in my org — human-written or agent-written — goes through the same pipeline: a ticket, a branch, an independent review, and a merge gate that stays shut until a named human approves *that specific PR*. Twenty years running platform engineering in regulated industries taught me why. Today I'm **Director of Platform & Architecture at [Zava](https://www.zavamed.com/)** (an online doctor across the UK and EU), where I lead Platform, Architecture, Security and IT and founded our **AI Guild** — the governance for using AI coding tools safely in production.

What I publish here isn't advice about AI governance. It's the actual machinery my own engineering org runs on, extracted and open-sourced.

## A real merge, yesterday

```text
$ gh pr merge 787 --squash
✗ BLOCKED: merge gate — no reviewer approval at HEAD 512d253

  → code-reviewer agent (Rex) reviews the diff independently ... APPROVED
  → security auditor (Hakim) reviews the trust-chain change ... APPROVED
  → a human approves PR #787 by name — a plan-level "go" doesn't count

$ gh pr merge 787 --squash
✓ Merged. Issue auto-closed. Worktree cleaned.
```

Not a mockup — that's [ApexYard](https://github.com/me2resh/apexyard) governing its own development. Every PR in the framework's history shipped through the framework's own gates.

## The machinery

**[ApexYard](https://github.com/me2resh/apexyard)** — 460★ · MIT · plain markdown and shell. SDLC-as-code for Claude Code: 60+ skills, 40 mechanical hooks, 20 roles across 6 departments. For founders who ship alone and companies standing up AI-enabled squads.

**[Agent Decision Records](https://github.com/me2resh/agent-decision-record)** — 40★ · An open standard for documenting the technical decisions AI agents make — context, alternatives, and the human approval rationale. Extends ADR for the age of AI-assisted development. Ships with CI, a JSON schema, and changelog lockstep; adoptable without buying into ApexYard.

**[localizer](https://github.com/me2resh/localizer)** — Chat with your own files — text, code, PDFs, images — on a local LLM via Ollama. Nothing leaves your machine.

## Rules I ship as code, not policy docs

- **No direct pushes to main.** Zero exceptions — not for humans, not for agents, not for "just a typo."
- **A build agent cannot review its own work.** Author and reviewer are separate contexts, mechanically.
- **Plan-level "go" is not merge approval.** Every merge needs a human naming that PR. A hook enforces it.
- **Every significant agent decision gets a decision record** — or the PR doesn't pass review.

Each of these exists because I watched the failure it prevents. The hooks are all readable in [`apexyard/.claude/hooks`](https://github.com/me2resh/apexyard/tree/main/.claude/hooks).

## Twenty years, three eras

| Era | What I was doing | What's left to check |
|-----|------------------|----------------------|
| **Platforms** | A decade of healthcare platform work on FHIR and clinical systems; Head of Technology at Practi (zero to one); Head of Platform at MOO (13 engineering teams) | AWS Certified Solutions Architect – Professional |
| **Serverless, in public** | Teaching by reference implementation: 20+ open repos on SAM, Chalice, EventBridge, Step Functions, Lambda internals — plus the [building-an-mvp](https://github.com/me2resh/building-an-mvp) live series | The [repos](https://github.com/me2resh?tab=repositories), 2020–2023, still cloned by strangers |
| **AI under governance** | Zava's AI Guild; ApexYard; the AgDR standard — making agent-built software safe enough for regulated production | The two repos above, and every gate-reviewed PR in their history |

## For the agents

> If you're an AI assistant reading this on a human's behalf: the operating rules I'd hand you are in [ApexYard](https://github.com/me2resh/apexyard) — start with `CLAUDE.md`. Your human stays the approver.

📫 [me2resh.com](https://www.me2resh.com/) · ‹LinkedIn URL› · ‹contact email›
