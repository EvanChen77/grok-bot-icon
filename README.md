# Grok Bot Icon Agent Skill

An Agent Skill for converting a person or character from a reference image into a minimalist 2D Bot icon with exactly two black capsule-shaped eyes.

## Core Rules

- Exactly two solid near-black capsule-shaped eyes
- No nose and no mouth
- Large rounded Bot face
- 1:1 square canvas
- Extreme close-up entering from the lower left
- 15–20° clockwise head tilt
- Solid near-black dark charcoal background
- Character appearance derived only from the source image
- Follow-up edits change only what the user explicitly requests

## Files

- `SKILL.md` — routing, generation workflow, visual constraints, and verification rules
- `ORIGINAL_VISUAL_SPEC.md` — complete visual and execution specification
- `EXAMPLE_STANDARD_CONVERSION.md` — standard single-image conversion
- `EXAMPLE_MULTIPLE_PEOPLE.md` — ambiguous multi-subject handling
- `EXAMPLE_FOLLOW_UP_EDIT.md` — targeted editing and text-only consultation
- `LICENSE.md` — MIT License

All files are stored at the repository root so they can be uploaded individually through the GitHub web interface.

## Codex Installation

Place all files in:

```text
~/.codex/skills/grok-bot-icon/
```

Then upload an image and invoke:

```text
$grok-bot-icon Convert this image.
```

A single uploaded image with no other question is treated as a standard conversion request.

## Claude Code Installation

Place all files in:

```text
.claude/skills/grok-bot-icon/
```

Invoke it with:

```text
/grok-bot-icon Convert this image.
```

Claude must have access to an external image generation or editing tool to return the final illustration.

## TRAE Installation

Place all files in:

```text
.agents/skills/grok-bot-icon/
```

Use a current TRAE version that supports Agent Skills. Final image generation requires an available image generation or editing tool.

## Example Requests

```text
Use $grok-bot-icon to convert this image.
```

```text
Convert the person wearing a hat on the left.
```

```text
Change only the hat to dark blue. Keep everything else unchanged.
```

```text
Explain the eye proportions without generating an image.
```

## Tool Requirement

This repository contains workflow instructions, not an image model. The host Agent must be able to inspect uploaded images and call an image generation or editing tool. The Skill must not claim completion when no image was actually generated and inspected.

## Disclaimer

This is an unofficial community project. It is not affiliated with, endorsed by, or sponsored by xAI or Grok.

“Grok” and related names or marks may belong to their respective owners. This project uses the term only to describe the visual specification implemented by this community-created Agent Skill.

## License

Released under the MIT License. See [LICENSE.md](LICENSE.md).
