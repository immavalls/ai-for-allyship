---
name: event-review
description: Review publicly available event materials for discoverable inclusion practices, source evidence, and constructive follow-up questions. Independent, CHAOSS-inspired, no badge or score.
---

# Community event review — experimental Claude-oriented skill

## When to use

A user asks to review a meetup, KCD, conference, workshop, or event page for inclusion practices. For content creation rather than assessment, use `guidance/` instead.

## Rules

1. **Scope first:** Identify event name, date, format, location, and URLs. Clarify if needed. Only make claims about the exact edition inspected.
2. **Source discipline:** Read supplied pages/accessible URLs. Where browsing is unavailable, say so and request the content. Do not claim to have inspected sites you did not access.
3. **Apply `checklist.md`:** Review the categories with direct evidence, quoting briefly or accurately paraphrasing and linking to the precise source page.
4. **Status vocabulary:** `Verified in source`, `Not located in reviewed sources`, `Needs organizer clarification`, or `Not applicable / not assessed`.
5. **Separate facts and recommendations:** A missing public link is an information-discovery gap, **not proof** that the event lacks a Code of Conduct or is unsafe.
6. **Celebrate positives:** Report clearly documented helpful practices, not just gaps.
7. **Respect people:** Do not infer the race, gender, sexuality, disability, or identities of speakers/attendees from photos, names, or biographies. Never use demographic estimates without reliable voluntary aggregate data.
8. **No invented outcomes:** No score, ranking, official badge, certification, or conclusion that an event is inclusive/exclusive overall. This is not an official CHAOSS review.
9. **Privacy:** Do not collect or expose sensitive reports, private demographic information, or private organizer correspondence.
10. **Human review:** Recommend specific questions and follow-ups for event organizers. Let humans decide whether and how to act.

## Output format

- **Scope and sources inspected:** name, edition/date, URLs, any inaccessible pages and review date.
- **What is documented well:** 2–5 source-grounded positives.
- **Evidence table:** criterion; status; source URL / supporting text; caveat or next step.
- **Three practical improvements:** prioritized as proposals, not accusations.
- **Questions for organizers:** unknowns that cannot be resolved from public information.
- **Limitations:** only publicly reviewed materials; independent experimental project; no CHAOSS affiliation or badge.

## Usage and output options

```
/event-review <url-or-event-info> [console|md|pdf]
```

The last word is the output format. It is optional:

- `/event-review https://example.org/event` -> **console** (default)
- `/event-review https://example.org/event md` -> Markdown file
- `/event-review https://example.org/event pdf` -> PDF file

Treat a trailing `console`, `md`, `markdown` or `pdf` (any case) as the format, not as part of the event URL or text. If the user asks in plain words instead ("as a PDF"), honour that too. If the format is unrecognised, use console and say which formats exist. If the format is omitted, use console and mention `md` and `pdf` in one line at the end.

- **console:** print the report in the conversation, following the output format above.
- **md:** write the same report to a `.md` file named `event-review-<event-slug>-<YYYY-MM-DD>.md` in the current directory (or a location the user names). Tell the user the path.
- **pdf:** write the Markdown report first, then convert it to PDF with whatever tool is available in the environment (for example `pandoc`, or a Python PDF library). Keep source links clickable and keep the "not a CHAOSS assessment" notice and a page footer. If no tool is available, or conversion fails, say so, keep the Markdown file, and don't claim a PDF exists. Check that the file was created and its text extracts correctly before reporting success.

Whatever the format, the content rules are identical: same sections, same status vocabulary, no score or badge, and the limitations section stays in. Disclose any conflict of interest the user mentions (for example, being an organizer of the event) in the report itself.

Saved reports are about real events and people. Write them where the user asks, and don't commit, publish or post them anywhere unless they ask you to.

## Background

The categories are inspired by the published [CHAOSS DEI Event Badging v4.0](https://www.chaoss.community/diversity-and-inclusion-badging/) criteria, which cover event demographics, inclusive experience at event, code of conduct, diversity access tickets, family friendliness, event accessibility, event location inclusivity, public health and safety, and (for virtual events) time inclusion. The official badge process uses human reviewers; do not reproduce their badge decisions.

See [`checklist.md`](checklist.md).
