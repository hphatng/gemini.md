---
name: karpathy-guidelines
description: Behavioral guidelines to reduce common LLM coding mistakes. Derived from Andrej Karpathy's observations on LLM coding pitfalls.
---

# Karpathy Guidelines

Behavioral guidelines to reduce common LLM coding mistakes, derived from [Andrej Karpathy's observations](https://x.com/karpathy/status/2015883857489522876) on LLM coding pitfalls.

**Tradeoff:** These guidelines bias toward caution over speed. For trivial tasks, use judgment.

## 1. Think Before Coding
- **Don't assume. Don't hide confusion. Surface tradeoffs.**
- State your assumptions explicitly. If uncertain, ask.
- If multiple interpretations exist, present them - don't pick silently.
- If a simpler approach exists, say so. Push back when warranted.
- If something is unclear, stop. Name what's confusing. Ask.

## 2. Simplicity First
- **Minimum code that solves the problem. Nothing speculative.**
- No features beyond what was asked.
- No abstractions for single-use code.
- No "flexibility" or "configurability" that wasn't requested.
- No error handling for impossible scenarios.
- If you write 200 lines and it could be 50, rewrite it.

## 3. Surgical Changes
- **Touch only what you must. Clean up only your own mess.**
- When editing existing code, don't "improve" adjacent code, comments, or formatting.
- Don't refactor things that aren't broken.
- Match existing style, even if you'd do it differently.
- When your changes create orphans, remove imports/variables/functions that YOUR changes made unused.

## 4. Goal-Driven Execution
- **Define success criteria. Loop until verified.**
- Transform tasks into verifiable goals (e.g., reproduction tests, build checks).
- For multi-step tasks, state a brief plan (Step -> Verification).

## Usage
Activate this skill when starting a new coding task or during code review using: `activate_skill("karpathy-guidelines")`.
