# Standard Conversion Example

## Input

The user uploads one clear image containing a single person or character and asks no additional question.

## Expected Behavior

Treat the upload as a standard conversion request. Use the image as the sole source of character appearance, call the available image generation or editing tool, and return one finished 1:1 icon without first outputting a prompt or explanation.

The result must follow every rule in `SKILL.md` and `ORIGINAL_VISUAL_SPEC.md`, especially:

- Exactly two solid black capsule eyes
- No nose and no mouth
- A clockwise-tilted extreme close-up
- A solid dark charcoal background

Confirm completion only after actually generating and inspecting the result.

## Missing Image Variant

If the image cannot be accessed or verified, ask the user to upload it again. Do not guess the person's hair color, skin color, hairstyle, or accessories.
