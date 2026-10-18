---
name: community-event-review
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

## Background

The categories are inspired by the published [CHAOSS DEI Event Badging v4.0](https://www.chaoss.community/diversity-and-inclusion-badging/) criteria, which address demographics practices, attendee experience, CoC, access tickets, family friendliness, accessibility, location inclusivity, and public health/safety. The official badge process uses human reviewers; do not reproduce their badge decisions.

See [`checklist.md`](checklist.md).
