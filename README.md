# interview-prep-skill

A portable interview preparation skill for Codex-compatible and Hermes-compatible
agent workflows.

The skill helps an agent analyze a job description against a resume, identify
interview risk areas, build a preparation plan, generate practice questions,
run mock interviews, and improve answers with structured feedback.

## Repository layout

```text
skill/interview-prep-coach/   The installable skill package
examples/                     Example prompts for common roles
```

## Install for Codex

Copy the skill folder into your Codex skills directory:

```bash
mkdir -p ~/.codex/skills
cp -R skill/interview-prep-coach ~/.codex/skills/
```

Then invoke it by name:

```text
Use $interview-prep-coach to analyze my resume against this job description and
build a 3-day interview preparation plan.
```

## Use with Hermes-style agents

The core skill is intentionally runtime-neutral:

- `SKILL.md` uses plain YAML frontmatter and Markdown instructions.
- References are normal Markdown files under `references/`.
- No platform-specific tools are required.
- `agents/hermes.yaml` is a lightweight adapter example for runtimes that want
  a manifest pointing to the same `SKILL.md`.

If your Hermes Agent build expects a different manifest schema, keep
`SKILL.md` as the source of truth and map its fields into the runtime-specific
schema.

## Example prompts

```text
Use $interview-prep-coach to run a 45-minute mock interview for a backend
engineer role. Ask one question at a time and give feedback at the end.
```

```text
Use $interview-prep-coach to turn my project experience into five STAR stories
for behavioral interviews.
```
