---
name: grok-bot-icon
description: Convert a person or character from a reference image into a minimalist 2D Grok bot icon. Also handles targeted follow-up edits and questions about the rules or prompt. A single uploaded image with no other question is treated as a conversion request.
---

# Grok Bot Icon Image Conversion

In this Skill, “Grok bot icon” refers only to the visual specification defined here. Character appearance must come exclusively from the source image. A separate style reference may inform style only; it must never supply the subject's skin color, hair color, hairstyle, or accessories.

Before generating, converting, or editing an image, read and follow [ORIGINAL_VISUAL_SPEC.md](ORIGINAL_VISUAL_SPEC.md) in full. The rules below are for routing and quick verification. If any summarized wording differs from the full specification, the full specification takes precedence.

Usage examples: [EXAMPLE_STANDARD_CONVERSION.md](EXAMPLE_STANDARD_CONVERSION.md), [EXAMPLE_MULTIPLE_PEOPLE.md](EXAMPLE_MULTIPLE_PEOPLE.md), and [EXAMPLE_FOLLOW_UP_EDIT.md](EXAMPLE_FOLLOW_UP_EDIT.md).

## Route the Request

- If the user uploads one visible source image and asks no other question, treat it as a standard conversion request. Call the available image generation or editing tool and return one finished icon.
- If the user explicitly asks to generate, convert, or edit an image, call the image tool directly. Do not first provide a prompt, production notes, explanation, or commentary. After successful generation, return the image without an added explanation.
- If the source image cannot be seen or verified, ask the user to upload it again. Do not infer the subject's appearance.
- If the image contains multiple people or characters and the user has not selected one, ask which subject to convert. Generate only after the subject is identified.
- If the roles of multiple uploaded images are unclear, ask which is the source image and which is the style reference.
- If the user only asks for prompt changes, rule explanations, result analysis, or usage instructions, answer in text only. Do not generate another image.
- For a follow-up edit, change only what the user explicitly requests. Preserve all unmentioned style rules and core character traits. If the source or existing result is unavailable but required for the edit, ask the user to upload it again.

## Generation Workflow

1. Inspect the source image. Identify the base face or surface color, hair color, and overall hairstyle silhouette. Preserve hair length, parting, curl pattern, distinctive bangs, and tied-hair structure. If the subject has no visible hair, preserve that state.
2. Select only recognition-critical traits from distinctive ears, hats, glasses, facial hair, accessories, and mechanical parts. Keep at most about three shape-based signature traits. Prefer large silhouettes and representative colors over small details. Never invent bangs, accessories, or mechanical parts absent from the source image.
3. Use the source image as the sole source of character appearance. Pass the actual source image to the image tool. For follow-up edits, also pass the existing generated image. If the tool cannot access the required images, do not claim to have converted or edited them.
4. Inspect the actual generated result. Correct visible hard-rule violations when the available tool and source material permit it, then inspect again. Never claim generation or verification without actually performing it.

## Face and Expression

- Use a large, rounded Bot face combined with simplified hair and recognition-critical traits. Use the subject's original skin or surface color in broad, smooth color shapes.
- Create cuteness through rounded proportions and the tilted composition. Do not rely on added facial expression marks.
- Join cheeks and chin smoothly. No pointed chin, angular jaw, or realistic bone structure. Do not copy the source expression or realistic facial anatomy.
- Draw absolutely no nose and no mouth, including a smile, dot mouth, or cat mouth.
- Optional blush must be two small, low-saturation oval color shapes coordinated with the face color. Blush must be flat, unoutlined, and free of highlights or sparkles. Leave clean face-color space around the eyes and blush.
- Keep glasses or facial hair only when essential for recognition, and simplify them. Glasses must not cover either eye. Facial hair must not function as a mouth or create realistic facial anatomy.

## Eyes: Highest Priority

- Draw exactly two near-black, solid-color capsule-shaped eyes. Each capsule is the complete eye and must contain no gaps.
- When the head is upright, each eye is a vertically elongated rounded bar with fully rounded ends and a height-to-width ratio of about 2.5:1 to 3:1.
- Both eyes must be identical in size and parallel. Each eye's long axis must be perpendicular to the line connecting the eye centers. When the head tilts, both eyes tilt with it while preserving this geometry.
- Never draw horizontal bars, closed eyes, hooks, base strokes, or shapes resembling the numeral “1.”
- Never add eyeballs, pupils, irises, sclera, reflections, highlights, sparkles, gradients, eyelashes, eyelids, eyebrows, or decorative outlines.
- These eye rules override the source image's original eye shape and color.

## Composition

- Use a 1:1 square canvas with exactly one character.
- Enlarge the face, hair, or full head silhouette so it fills most of the canvas, as if the character is leaning into the frame from the lower left.
- Tilt the entire head clockwise by about 15–20 degrees. The eye on the image's left must sit slightly higher than the eye on the right. Face, eyes, hair, and attached accessories must share the same overall tilt.
- Crop the head naturally at the left and bottom canvas edges. The chin must touch or extend beyond the bottom edge. Leave a clearly visible area of dark background in the upper right.
- Both eyes must remain fully visible and unobstructed by hair or accessories.
- Avoid a small fully visible centered head, passport-photo framing, or perfect bilateral symmetry.
- Do not draw the body or hands. Retain only a minimal amount of neck or collar at the bottom when essential for recognition.

## Hair, Accessories, and Color

- Simplify hair into a few large, smooth, clear shapes. Do not render many individual strands. Preserve the source's bang direction, perceived length, and overall hairstyle silhouette.
- Use minimalist flat 2D rendering with almost no outlines. Do not use heavy black outlines. Separate structures mainly through differences between adjacent color shapes.
- Use representative colors from the source image in flat, soft coloring. Add no more than one broad, subtle, soft shadow layer. If hair highlights are needed, use only one or two large highlight shapes.
- Reduce accessories and mechanical parts to their overall silhouette and large connecting structures. Omit tiny screws, wires, circuits, dense panel lines, and complex patterns.
- At small avatar size, the two black capsule eyes and the character's core silhouette must remain immediately recognizable.

## Background and Prohibited Elements

- Fill the entire canvas with a solid near-black dark charcoal background. Add no objects or patterns.
- Do not include circular frames, badge borders, text, numbers, logos, watermarks, speech bubbles, exclamation marks, glitter, particles, glows, or lens flares. Never write the production rules inside the image.
- Avoid photorealism, 3D rendering, oil-paint texture, rough sketch lines, excessive gloss, complex lighting, many loose hair strands, or dense decoration.

## Fixed Conflict Priority

1. Two undecorated black capsule eyes.
2. A rounded Bot face with no mouth and no nose.
3. A tilted extreme close-up in which both eyes are fully visible.
4. Source-image base colors and core recognition traits.
5. All other details.

If bangs cover the eyes, preserve their main direction while adjusting their length, width, or position so both eyes remain fully visible. If cropping completely removes a core accessory, slightly adjust the subject's scale or position to retain a recognizable portion. Never create a feature absent from the source image.

## Delivery and Verification

For an image-generation request, return only the actually completed icon. Verify the number, geometry, solid fill, and visibility of the eyes; the absence of nose and mouth; the square extreme close-up, tilt, cropping, and upper-right negative space; the source of character traits; the dark charcoal background; and all prohibited elements. Never say the image is generated or verified unless it was actually generated and inspected.
