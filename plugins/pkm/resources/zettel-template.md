# Zettelkasten Zettel Template

This template is used by the `teach-me-personal` skill to generate the final
takeaway as a Zettelkasten-compatible Zettel note.

---

## Template

```markdown
---
id: YYYYMMDDHHMMSS
title: "Short declarative title of the concept or session"
topic: "Domain or subject area"
tags:
  - learning
  - <domain-tag>
  - <concept-tag>
audience: junior | senior | non-technical
session-count: 1
date: YYYY-MM-DD
source-skill: teach-me-personal
upstream: https://github.com/noVaSon/teachme-chat
---

# <title>

> **Purpose:** Why I learned this — what I'm using it for.

## Concepts

<!-- One section per concept, in dependency order. -->

### <Concept Name>

<2–4 sentences in my own words.>

`Source:` AI-authored (Claude, YYYY-MM), certainty <high|medium|low> — <verification note or primary source URL>

---

### <Concept Name>

<2–4 sentences in my own words.>

`Source:` <source>

---

## Misconceptions

<!-- Only misconceptions that genuinely surfaced in this session, never invented. -->

- **Wrong belief:** <what I thought>  
  **Correction:** <what is actually true>

## Further Study

<!-- Concepts parked or flagged for follow-up. -->

- <topic> — <why it was parked or what to verify>

## References

<!-- Verified primary sources used during the session. -->

- <Author (Year). Title. URL>
```

---

## Field Reference

| Field | Description |
|---|---|
| `id` | Timestamp slug (YYYYMMDDHHmmss) — unique Zettel identifier |
| `title` | Short declarative title of the main insight |
| `topic` | Domain or subject area (e.g. "distributed systems", "music theory") |
| `tags` | 2–5 lowercase kebab-case tags; always include `learning` |
| `audience` | Calibrated depth: `junior`, `senior`, or `non-technical` |
| `session-count` | How many sessions this Zettel covers |
| `date` | ISO 8601 date of the session (`YYYY-MM-DD`) |
| `source-skill` | Always `teach-me-personal` for notes from this skill |
| `upstream` | Link to the original teach-me-chat skill |
