---
name: instagram-content-calendar
description: Plan 1–4 weeks of Instagram photo posts, carousels and Reels from the user's goals and content pillars, or repurpose a blog post, video or transcript, draft every slot, and schedule them with the PostOnce Instagram MCP. Use when the user asks for an Instagram content calendar, content plan, posting schedule, Instagram post ideas, or to turn one piece of content into a week of Instagram posts.
metadata:
  author: PostOnce
  version: "0.1.0"
---

# Instagram content calendar

Plan a realistic run of Instagram posts, draft each one, and schedule them once the user approves.

## Before planning

Get or infer:
- Goal: followers, saves and shares, profile visits, leads, sales, bookings.
- 3 to 4 content pillars (teach, show the work, proof, personality or community).
- How many weeks (1 to 4) and how many posts a week the user can actually make. 3 to 5 is a good default; consistency beats volume.
- What they can produce: photos, screen recordings, talking-head video, designed slides.
- Timezone and any fixed dates (launches, events, sales).
- Or a source to repurpose: a blog URL, video, podcast transcript or newsletter. Pull 5 to 10 distinct ideas from it; each post carries one.

## Build the plan

Mix formats so the grid doesn't repeat, and match each idea to the format that suits it:

| Format | Use it for | Skill |
| --- | --- | --- |
| Reel (single video) | Hooks, demos, behind the scenes, reaching new people | `instagram-reel-script` |
| Carousel (2–10 items) | Tips, steps, before/after, stories worth saving | `instagram-carousel-maker` |
| Photo post | Announcements, products, moments, quotes | `instagram-caption-generator` |

Stories can't be published through this server, so leave them out of the scheduled plan. If the user wants Story ideas, list them separately for them to post in the app.

Give the plan as a table: date and time, pillar, format, hook or first line, media needed, status. Spread pillars across the week. Put the strongest idea early in the run. Post times: use the user's own best times if they know them; otherwise pick consistent times when their audience is likely awake and say it's a starting point to test.

## Draft each slot

For every slot, write the full caption with the `instagram-caption-generator` rules (first line, CTA, 3 to 5 hashtags) and a media brief: what to shoot or design, aspect (4:5 for photos and carousels, 9:16 for Reels), and cover text for Reels. Keep captions under 2,200 characters.

## Schedule

Instagram posts need media, so a slot can only be scheduled once its photos or video exist.
- Slots with media ready: upload with `create_upload_url`, then `create_post` with `media` and `publish_at` (ISO timestamp with the user's timezone offset).
- Slots still waiting on media: save with `create_draft` so the copy is ready when the media is.
- To post the same slot to other platforms too, add their accounts as targets and adjust copy with `content_override`.

## Output

Return the calendar table, then each slot's draft. Ask for approval before scheduling anything. After approval, confirm the Instagram account, create the posts, then list each post ID with its scheduled time from `get_post`. Scheduled posts can be changed with `update_post` or cancelled with `cancel_post` until they go out.
