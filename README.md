# AI Instructions: Results Over Activity

**Practical instructions for AI assistants and coding agents that prioritize working results, simple solutions, and the user's time.**

AI can write code in seconds. It can also spend hours solving the wrong problem, add dependencies nobody needed, or break a working feature while making a tiny change.

This repository contains **14 rules** designed to reduce those failures. They tell an assistant *how to approach work*: understand the goal, use the simplest viable solution, protect existing systems, verify the outcome, and communicate honestly.

**[Read the complete instructions →](./GLOBAL_AI_INSTRUCTIONS.md)**

## Why this exists

These rules grew out of real-world AI-assisted work: building websites, debugging applications, evaluating tools, and delivering projects under time and budget constraints.

The recurring problem wasn't a lack of code generation. It was **unnecessary work**:

- Replacing a working feature instead of making a small fix.
- Introducing custom code when the platform already has the needed feature.
- Choosing a technically possible tool that is awkward in actual use.
- Treating an implementation report as proof that something works.
- Asking the user to perform routine diagnosis the assistant could handle.
- Spending tokens, time, or money on work that doesn't advance the goal.

The objective is straightforward: **less avoidable complexity, fewer regressions, more usable results.**

## The principles

| Principle | What the assistant should do |
| --- | --- |
| Understand first | Clarify the real goal, requirements, constraints, and success criteria. |
| Prefer the simplest solution | Check native features and existing components before writing new code. |
| Test the critical workflow | Validate the main use case before scaling an approach. |
| **Don't break what works** | Inspect the current state, make minimal changes, and plan for rollback. |
| Fix the root cause | Diagnose before patching symptoms or adding workarounds. |
| Respect the user's resources | Protect time, money, usage limits, deadlines, and commercial interests. |
| Verify before declaring success | Separate **implemented**, **verified**, and **ready for delivery**. |
| Communicate clearly | Be concise, surface uncertainty, and don't claim untested results. |

The [full file](./GLOBAL_AI_INSTRUCTIONS.md) covers these and six additional rules, including agent delegation, complete replacement code, and step-by-step guidance.

## Quick start

1. Open **[GLOBAL_AI_INSTRUCTIONS.md](./GLOBAL_AI_INSTRUCTIONS.md)**.
2. Copy the rules into the persistent instructions supported by your assistant or coding tool. For agents that read `AGENTS.md`, you can incorporate the text into that file. For chat assistants, use project or custom instructions where supported.
3. **Merge with your existing instructions** instead of blindly overwriting them. Adjust the wording to your workflow and the tool's instruction-length limits.
4. Try the rules on one small, real task, and check whether the assistant's behavior improves.

The file is plain Markdown: **no installation, account, runtime, or dependencies required.** Instruction-file support varies by tool, and higher-priority system, safety, and permission rules still apply.

## What this looks like in practice

### Example 1 — A minor website change

**Request:** “Make the quantity buttons larger.”

**Expected approach:** Inspect the existing component and styles. Change only what's needed. Check the desktop and mobile layouts, and make sure the cart still works. Don't rebuild the cart or introduce a new JavaScript handler without a reason.

### Example 2 — Choosing a tool

**Request:** “I need an easy way to crop images visually.”

**Expected approach:** Test actual visual cropping before recommending the tool. A library that accepts crop coordinates but has no visual editor may be technically capable yet unsuitable for the user.

### Example 3 — Reporting completion

**Request:** “Fix the broken checkout flow.”

**Expected approach:** Find the cause, make a targeted change, and run the relevant checkout scenario. Report what changed, what was verified, and what couldn't be tested. Don't call it production-ready based only on a successful code edit.

*These examples illustrate the intended behavior; they are not benchmark results or guarantees.*

## Who it's for

- **Solo builders and vibe coders** who want a reliable collaborator, not extra work.
- **Developers and technical teams** using AI to maintain existing codebases.
- **Freelancers and agencies** where regressions, wasted time, and unclear handoffs have real costs.
- **Anyone using coding agents** who values practical outcomes over elaborate workflows.

## Scope and limitations

This is an **instruction set**, not an autonomous agent, test suite, or code-quality guarantee. It cannot replace access to the current code, meaningful acceptance tests, or human judgment on high-impact decisions. Results will vary by model, tool, task, and context.

The rules are intentionally opinionated. Adapt them to your needs rather than treating every line as universal.

## Feedback

Found a rule that prevented a mistake—or one that made an agent less effective? [Open an issue](https://github.com/OlleMax/ai-instructions/issues) with a concrete example. Specific before/after behavior is especially useful.

---

**Core idea:** Understand the task → choose the simplest approach → test the key workflow → implement → verify → deliver.

**Do not break what works. Do not add unnecessary complexity. Do not waste the user's time.**
