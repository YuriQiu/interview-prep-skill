---
name: interview-prep-coach
description: Use this skill when the user wants to prepare for job interviews, analyze a job description against their resume, generate interview practice questions, run mock interviews, improve behavioral answers with STAR structure, prepare company-specific talking points, or build a day-by-day interview preparation plan.
metadata:
  short-description: Interview preparation coach
---

# Interview Prep Coach

## Compatibility

This skill is designed to work in Codex and other agent runtimes that can read a
`SKILL.md` file. Keep the workflow portable:

- Use plain Markdown outputs unless the user asks for another format.
- Do not require platform-specific tools.
- If files, web access, or calendars are available, treat them as optional.
- Keep resume, compensation, and personal background details confidential.
- Do not invent candidate experience. Reframe truthfully and call out gaps.

## Intake

Ask only for missing information that materially changes the preparation plan.
Useful inputs:

- Target role, level, company, and interview date.
- Job description or recruiter notes.
- Resume, LinkedIn summary, or project list.
- Interview stage: recruiter screen, hiring manager, technical, case, panel, or
  final round.
- Time available: same-day, 2-3 days, 1 week, or longer.
- Candidate concerns: weak area, career gap, job change, compensation, language,
  confidence, or a specific interviewer.

When the user has not provided enough information, proceed with a default
general preparation mode and list assumptions briefly.

## Core Workflow

1. Build the role scorecard.
   Identify the 5-8 capabilities the interviewer is likely to test. Separate
   must-have signals from nice-to-have signals.

2. Map evidence from the candidate.
   Match resume/projects to the scorecard. Mark each area as strong, usable,
   weak, or missing. Prefer concrete evidence: scope, decisions, metrics,
   tradeoffs, collaboration, and outcomes.

3. Identify interview risks.
   Look for gaps between the job description and the candidate evidence. Create
   truthful mitigation talking points and practice questions for each risk.

4. Create a preparation plan.
   Choose a plan length based on available time. Include daily work blocks for
   knowledge review, answer drafting, mock practice, and final review.

5. Practice in loops.
   For mock interviews, ask one question at a time. Wait for the answer, then
   continue with a realistic follow-up. Do not reveal the full evaluation until
   the round is complete unless the user asks for coaching mode.

6. Deliver a final packet.
   End with a concise pack containing target stories, likely questions,
   high-risk answers, company talking points, and questions to ask the
   interviewer.

## Modes

Use the mode that best matches the user's request:

- **JD/resume analysis**: scorecard, evidence map, gaps, and positioning.
- **Preparation plan**: day-by-day tasks with priorities and practice blocks.
- **Question bank**: likely questions grouped by interview round and skill.
- **Answer repair**: rewrite one answer for clarity, credibility, and structure.
- **Mock interview**: one question at a time, realistic follow-ups, final rubric.
- **Story bank**: convert experience into reusable STAR/CAR stories.
- **Final review**: short rehearsal sheet for the last 30-60 minutes.

## Output Standards

For analysis, prefer this structure:

```markdown
## Role Scorecard
## Candidate Match
## Risk Areas
## Preparation Plan
## Practice Questions
## Final Review Pack
```

For answer feedback, use:

```markdown
## Quick Verdict
## What Works
## What To Improve
## Stronger Version
## Follow-up Drill
```

For mock interviews, use a score from 1-5 only at the end:

- 5: clear, specific, credible, senior-level signal.
- 4: solid answer with minor missing detail.
- 3: acceptable but generic or under-supported.
- 2: unclear, risky, or missing interviewer signal.
- 1: likely damaging or non-responsive.

## Reference Loading

Load these files only when relevant:

- `references/behavioral.md` for STAR/CAR stories, leadership, conflict,
  failure, motivation, and culture-fit answers.
- `references/technical.md` for software engineering, systems, architecture,
  debugging, and technical communication interviews.
- `references/product.md` for product sense, execution, strategy, metrics, and
  product leadership interviews.
- `references/data.md` for analytics, SQL, experimentation, metrics, statistics,
  and data case interviews.
- `references/recruiter.md` for recruiter screens, career narrative, motivation,
  compensation, logistics, and closing questions.

Use `assets/interview-plan-template.md` when the user asks for a reusable plan
or a written preparation artifact.
