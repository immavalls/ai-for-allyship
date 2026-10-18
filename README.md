# AI for Allyship and Inclusion

**Early prototype — community-first guidance for AI-assisted content creation and event reviews.**

AI can help organize meetups, conferences, and open-source communities, but it can also reproduce exclusionary language, stereotyped imagery, and omissions. This project helps organizers **spot and reduce those problems earlier**, without replacing human judgment.

Inspired by real experiences organizing cloud-native events: AI-generated invitations that emphasize exclusivity and status; technical workshop illustrations reinforcing gender stereotypes; homogenous default AI-generated meetup images; and event descriptions missing accessible Code of Conduct information.

This project was introduced in [AI for Allyship and Inclusion: Supporting CNCF Communities with Context-Aware AI](https://eyeveebee.dev/ai-for-allyship-and-inclusion-supporting-cncf-communities-with-context-aware-ai) at KCD UK 2026.

## Start here — two workflows

### CREATE: make more welcoming content

Paste the relevant guidance into **Claude, ChatGPT, Gemini, or another assistant** as instructions before asking for content. These are portable Markdown instructions, not automatically installed integrations.

- **Event announcements / emails / posts:** [Inclusive writing](guidance/inclusive-writing.md) + [English](languages/en.md) or [Spanish](languages/es.md).
- **Meetup and workshop visuals:** [Inclusive imagery](guidance/inclusive-imagery.md). Review outputs; prompt guidance cannot guarantee representation.
- **Event pages:** Add [Community safeguards](guidance/community-safeguards.md) to the writing instructions.

**Example prompt:**

> Follow the guidance in `guidance/inclusive-writing.md` and `languages/en.md`. Draft a short invitation for a community meetup about OpenTelemetry. Keep it welcoming to people with varied experience, avoid status-based gatekeeping, and flag any missing event accessibility or Code of Conduct details rather than inventing them.

See [example invitation](examples/event-announcement.md) and [example image prompt](examples/image-prompt.md).

### REVIEW: flag publicly visible gaps in an event

Start with the [Claude-oriented event-review skill](skills/event-review/SKILL.md) and [checklist](skills/event-review/checklist.md). Provide an event URL or copied public event information and ask for an **evidence-based preliminary review**. If browsing is unavailable, provide source material; never allow the assistant to invent having visited a website.

Example prompt:

> Use the event-review skill and checklist to review this event website: [URL]. Give sources and direct quotes or precise paraphrases for every finding. Separate verified information, information not found in the inspected pages, and questions for organizers. No badges, scores, or claims about actual attendee experiences.

See the [sample report format](examples/event-review.md).

## What this is (and isn't)

- **Is:** a starter kit for prompting, human review, and constructive feedback in community operations.
- **Is not:** a certified bias detector, exhaustive event audit, a substitute for people with lived experience, or an official CHAOSS assessment.
- **Current state:** Markdown guidance, examples, and an experimental Claude-oriented skill; no automated integrations, benchmarks, or validated event assessments yet.
- **Principle:** Ask *who might be missing?* and *what information might be missing?* rather than assuming an image or webpage tells the whole story.

## Repository map

```text
guidance/               Inclusive writing, imagery, and event safeguards
languages/              English and Spanish writing notes
skills/event-review/    Experimental Claude-oriented event review workflow
examples/               Copyable illustrative starting points
references/RESOURCES.md Further reading, acknowledgments, and links
CONTRIBUTING.md         How to help improve the project
```

## Attribution and community

Inspired in part by Jorge Ordovás's [DEI Companion](https://github.com/joobid/DEI-companion), especially its emphasis on actionable allyship and curated learning resources. The event-review workflow also draws on the publicly available [CHAOSS DEI Event Badging v4.0 criteria](https://www.chaoss.community/diversity-and-inclusion-badging/). **This project is independent of CHAOSS and does not issue CHAOSS badges.** The official program uses human peer review.

See [resources and acknowledgments](references/RESOURCES.md) and my [inclusive speaker rider](https://eyeveebee.dev/creating-my-inclusive-speaking-rider).

## License

Apache-2.0 — see the existing [`LICENSE`](LICENSE) in the repository. Contributions are welcome under the repository's license.
