---
name: instagram-carousel-maker
description: Plan, write and build an Instagram carousel (2–10 slides at 1080×1350) with its caption, then publish or schedule it with the PostOnce Instagram MCP. Use when the user asks for an Instagram carousel, a carousel maker or carousel template, swipeable slides, or to turn a blog post, thread, tips list or photo set into a carousel.
metadata:
  author: PostOnce
  version: "0.1.0"
---

# Instagram carousel maker

Instagram carousels take 2 to 10 items. Photos and videos can be mixed; each carousel video must be 3 to 60 seconds. This skill plans the slides, builds them as images, and hands the post to the `postonce` skill.

## Size and format

- Make every slide 1080×1350 (4:5). It's the tallest feed shape Instagram accepts; taller images, like 9:16 phone screenshots, get rejected. Use 1080×1080 only if the user wants square.
- Keep all slides the same size. Instagram crops mixed shapes to match.
- Export JPEG or PNG under 8 MB each. PostOnce publishes them as JPEG. GIFs aren't supported.
- Keep text away from the outer 60 px; the grid preview and profile view crop edges.

## Plan the slides

Use 6 to 10 slides for a tips, story or tutorial carousel. Write the plan before any design:

| Slide | Job | Words |
| --- | --- | --- |
| 1. Cover | The hook: a result, a number or the reader's problem. Must work alone in the feed. | 10 or fewer |
| 2. Setup | Why this matters, or the mistake most people make. | 15–25 |
| 3–N. Body | One point per slide, numbered if it's a list. | 10–30 each |
| Last | One takeaway plus one ask: save, share, comment or follow. | 15 or fewer |

Rules that hold up across strong carousels:
- One idea per slide, large type, the same layout and colors on every slide so it reads as one piece.
- Give people a reason to swipe: an open loop on the cover, or "Swipe →".
- Real photos, screenshots and numbers beat stock images and icons.
- Instagram may show the second slide to people who skipped the first, so slide 2 should also hook.
- Avoid paragraphs on slides. If a slide needs more than 30 words, split it.

## Build the images

If the environment can render HTML to PNG (headless Chrome or Playwright), build each slide as a fixed 1080×1350 HTML page with the user's fonts and colors, and screenshot each one. Check every PNG opens at the right size before uploading. Otherwise, give the user the slide text and layout notes for Canva, Figma or another design tool.

If the user already has photos, check the count (2 to 10), the aspect (between 4:5 and 1.91:1), and the order they want.

## Caption

Write the caption with the `instagram-caption-generator` rules: a first line that adds to the cover, a short body that says why the slides are worth saving, one CTA, 3 to 5 specific hashtags. Don't repeat every slide in the caption. Include alt text per slide for the user to add in the app later; the API doesn't set it.

## Output

Return the slide plan (slide number, headline, supporting text, visual note), the rendered files if you made them, then the caption. To publish, upload each slide with `create_upload_url`, confirm each upload succeeded, and pass the public URLs in slide order as `media` in `create_post` (see the `postonce` skill). Confirm the Instagram account and the time before calling `create_post`.
