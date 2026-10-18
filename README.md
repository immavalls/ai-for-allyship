# AI for Allyship and Inclusion

**Early prototype — community-first guidance for AI-assisted content creation and event reviews.**

AI can help organize meetups, conferences, and open-source communities, but it can also reproduce exclusionary language, stereotyped imagery, and omissions. This project helps organizers **spot and reduce those problems earlier**, without replacing human judgment.

Inspired by real experiences organizing cloud-native events: AI-generated invitations that emphasize exclusivity and status; technical workshop illustrations reinforcing gender stereotypes; homogenous default AI-generated meetup images; and event descriptions missing accessible Code of Conduct information.

This project accompanies the KCD UK 2026 talk (19 October 2026) [AI for Allyship and Inclusion: Supporting CNCF Communities with Context-Aware AI](https://eyeveebee.dev/ai-for-allyship-and-inclusion-supporting-cncf-communities-with-context-aware-ai). Slides: <https://bit.ly/ai-for-allyship-2026>.

> **AI won't make our communities inclusive. People will. But we can build AI tools that help us become better allies.**

## Why this exists

The project grew out of things I (Imma) saw while organizing and attending technology communities:

- **Exclusionary wording.** A community's AI-generated promotional text called it an "exclusive community of top-tier engineers" and used phrases like "highly selective" and "high-signal and low-noise", while organizers were puzzled by low female attendance. One phrase doesn't prove discrimination, but the AI never challenged the framing, and the community had no Code of Conduct.
- **Stereotyped imagery.** In workshop material for a conference, developers were depicted as young men and operators as young women, everyone white. Nobody noticed at first, which shows bias can be normalized by both AI generation and human review.
- **Homogeneous defaults.** Default prompts for a Cloud Native Barcelona meetup image produced mostly male, similar-looking groups. Explicitly asking for variety in gender, age, and skin tone helped a lot, but it should not depend on organizers remembering every time.
- **Missing Code of Conduct.** When drafting meetup announcements, AI doesn't ask whether a Code of Conduct exists or link it.

The aim isn't to remove human judgment, just to make good intentions repeatable.

## Start here — two workflows

### CREATE: make more welcoming content

Paste the relevant guidance into **Claude, ChatGPT, Gemini, or another assistant** as instructions before asking for content. These are portable Markdown instructions, not automatically installed integrations.

- **Event announcements / emails / posts:** [Inclusive writing](guidance/inclusive-writing.md) + [English](languages/en.md) or [Spanish](languages/es.md).
- **Meetup and workshop visuals:** [Inclusive imagery](guidance/inclusive-imagery.md). Review outputs; prompt guidance cannot guarantee representation.
- **Event pages:** Add [Community safeguards](guidance/community-safeguards.md) to the writing instructions.

### Using the guidance in Claude, ChatGPT, or Gemini

The guidance is plain Markdown, so the portable approach is the same everywhere: paste the files into the conversation (or into a custom-instructions / project / Gem / custom GPT field if your plan has one) before asking for content. Platform differences are *not yet tested by this project*; if you try it, please [open an issue](../../issues) with what worked and what didn't. Known constraints: image generation depends on each tool's image model, and web browsing for reviews depends on your plan and settings.

**Example prompt:**

> Follow the guidance in `guidance/inclusive-writing.md` and `languages/en.md`. Draft a short invitation for a community meetup about OpenTelemetry. Keep it welcoming to people with varied experience, avoid status-based gatekeeping, and flag any missing event accessibility or Code of Conduct details rather than inventing them.

See [example invitation](examples/event-announcement.md) and [example image prompt](examples/image-prompt.md).

### REVIEW: flag publicly visible gaps in an event

Start with the [Claude-oriented event-review skill](skills/event-review/SKILL.md) and [checklist](skills/event-review/checklist.md). Provide an event URL or copied public event information and ask for an **evidence-based preliminary review**. If browsing is unavailable, provide source material; never allow the assistant to invent having visited a website.

**Installing the skill (Claude Code):** copy the `skills/event-review/` folder (both `SKILL.md` and `checklist.md`) into `.claude/skills/event-review/` in your project, or `~/.claude/skills/event-review/` for personal use, then ask Claude to review an event. In other Claude surfaces, or any other assistant, paste `SKILL.md` and `checklist.md` into the conversation instead. Skill loading is experimental here and has not yet been tested across surfaces.

Example prompt:

> Use the event-review skill and checklist to review this event website: [URL]. Give sources and direct quotes or precise paraphrases for every finding. Separate verified information, information not found in the inspected pages, and questions for organizers. No badges, scores, or claims about actual attendee experiences.

See the [sample report format](examples/event-review.md).

**Output format:** ask for `console` (default), `markdown` (saves a `.md` file) or `pdf` (saves a PDF if your environment has a conversion tool; otherwise you get the Markdown file and a note). Example: *"Review this event and give me the result as a PDF."* PDF output depends on tools available where the assistant runs and is not yet tested across surfaces.

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

## Contributing

Real (anonymized) test cases, false positives, Spanish and English language nuance, and better references are all welcome. See [CONTRIBUTING.md](CONTRIBUTING.md).

## Attribution and community

Inspired in part by Jorge Ordovás's [DEI Companion](https://github.com/joobid/DEI-companion), especially its emphasis on actionable allyship and curated learning resources. The event-review workflow also draws on the publicly available [CHAOSS DEI Event Badging v4.0 criteria](https://www.chaoss.community/diversity-and-inclusion-badging/). **This project is independent of CHAOSS and does not issue CHAOSS badges.** The official program uses human peer review.

See [resources and acknowledgments](references/RESOURCES.md) and my [inclusive speaker rider](https://eyeveebee.dev/creating-my-inclusive-speaking-rider).

## License

Apache-2.0 — see the existing [`LICENSE`](LICENSE) in the repository. Contributions are welcome under the repository's license.
