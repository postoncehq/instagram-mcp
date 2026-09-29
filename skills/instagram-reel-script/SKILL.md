---
name: instagram-reel-script
description: Write an Instagram Reel script with hook options, timed beats, on-screen text, cover text and the caption, then publish or schedule the finished video with the PostOnce Instagram MCP. Use when the user asks for a Reel script, Reel ideas, Reel hooks, what to say in a Reel, or to turn a blog post, tip or product into a short video for Instagram.
metadata:
  author: PostOnce
  version: "0.1.0"
---

# Instagram Reel script

Write a script the user can film in one go, then publish the finished video as a Reel with the `postonce` skill.

## Before writing

Get or infer: who's on camera (face, voiceover, hands only, screen recording), the one takeaway, the target length, and any proof (a number, a before/after, a demo). If the source is long, pick one idea. Never invent results or testimonials.

Default to 15 to 45 seconds. Longer Reels work when every beat earns its place; the API accepts 3 seconds to 15 minutes.

## The hook (first 1–3 seconds)

Write three hook options and recommend one. Each hook is spoken line plus on-screen text plus the first shot, and all three should land in the first second or two.

| Pattern | Spoken line shape |
| --- | --- |
| Result first | "This took us from [real before] to [real after] in [time]." (only with real numbers) |
| Callout | "If you post Reels and they die at 200 views, watch this." |
| Mistake | "Stop filming Reels like this." |
| Visual payoff | Show the finished thing first, then "here's how." |
| Contrarian | "Posting every day is why your Reels flop." |

Anti-patterns: "Hey guys, welcome back", a logo intro, a slow pan before anything happens, or hook text that says something different from the voice.

## Beats

Write the script as a table, one row per shot:

| Time | Shot | Spoken / voiceover | On-screen text |
| --- | --- | --- | --- |

- Change the shot or the text every 2 to 4 seconds.
- Put the payoff before the end, then close fast. A loop back to the first line helps rewatches.
- Keep on-screen text short, high contrast, and out of the bottom fifth and the right edge, where Instagram's caption and buttons sit.
- Assume many people watch muted: the on-screen text should carry the story on its own.
- End with one ask: follow for part 2, save this, comment a word, or link in bio.

## Cover

Write 3 to 6 words of cover text that say what the Reel is about. Frame it 1080×1920 (9:16) with the text centered, since the profile grid crops the cover. Publishing passes the cover as `thumbnail_url` (JPEG or PNG, 8 MB or less).

## Caption

Write a short caption with the `instagram-caption-generator` rules: a first line that adds context, one CTA, 3 to 5 specific hashtags.

## Output

Return: recommended hook plus two alternatives, the beat table, cover text, the caption, and a one-line shot list. When the user has the video file (MP4 or MOV, up to 1 GB, 9:16), upload it and the cover with `create_upload_url`, then call `create_post` with the video in `media` and `thumbnail_url` set. If the video used AI generation, offer `platform_options: {"ai_generated": true}`. Confirm the Instagram account and the time before posting.
