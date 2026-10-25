# Multiple-People Image Example

## Input

The user uploads an image containing three people and says, “Make this a Grok bot icon,” without selecting a subject.

## Expected Behavior

Ask one short question:

```text
Which person should I convert: left, center, or right?
```

After the user identifies the subject, convert only that person. Do not include other people in the finished image or mix their hair, skin color, clothing, or accessories into the selected subject.

## Source and Style Reference Variant

If the user uploads both a subject image and a style reference but does not identify their roles, ask which image is the source. The style reference must never supply character appearance.
