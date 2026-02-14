# halo-ticket-agent

Policy-driven “agent-style” ticket cleaner for Halo notes (NHS IT, second-line).

This repo demonstrates how to turn messy support notes into a consistent Halo ticket update **plus** remit-safe suggested next steps, using:
- clear output schemas
- routing rules (handover vs handle)
- severity rules
- escalation triggers

> **Safety note:** This project is designed for *sanitised* operational text. Do **not** paste patient-identifiable information (PII) or clinical content. The examples here are fictional.

## What it does

Given raw notes, it produces:

1) **Cleaned ticket fields** (User, Location, Device, Category, Short/Long description, Impact, Scope, Duration, Troubleshooting performed)  
2) **Severity flag** (High/Medium/Low + reason)  
3) **Next actions** (second-line appropriate), or **Routing handover** if it belongs to another team (Epic / Apogee printing / Network / Telephony)

## How it works (agent thinking)

The workflow is policy-first:

1. **Classify** into a bounded set of categories  
2. **Route away** if the request belongs to another resolver group  
3. **Check sufficiency** (what’s missing)  
4. **Assess severity** (patient-care impact, scope, time open)  
5. **Apply escalation triggers** per category  
6. **Generate output** in a fixed schema

## Contents

- `prompts/halo_agent_prompt_v1.txt` — Master prompt template (second-line + routing + severity + escalation policy)
- `policies/` — Rules in human-readable form:
  - `routing_rules.md`
  - `severity_rules.md`
  - `escalation_rules.md`
- `examples/` — Fictional before/after pairs you can use as a demo

## Usage

This repo is **docs-first**. You can:
- Use the prompt template directly in ChatGPT / an internal LLM tool
- Later, plug it into a CLI or workflow engine

Suggested workflow:
1. Copy `prompts/halo_agent_prompt_v1.txt`
2. Paste into your LLM tool
3. Add raw notes under `--- RAW NOTES ---`
4. Use the structured output in Halo

## Future work

- Minimal Python CLI wrapper (read notes → run prompt → save output)
- Unit tests for classification/routing heuristics
- Config file for local team variations (thresholds, categories)
- Optional redaction pre-pass (strip obvious identifiers)
