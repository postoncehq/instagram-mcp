---
name: instagram-caption-generator
description: Write Instagram captions for photo posts, carousels and Reels with a strong first line, a clear CTA, a few specific hashtags and suggested alt text, ready to publish with the PostOnce Instagram MCP. Use when the user asks for an Instagram caption, caption ideas, a caption generator, or to write, rewrite or shorten a caption for a post or Reel.
metadata:
  author: PostOnce
  version: "0.1.0"
---

# Instagram caption generator

Write one caption for one Instagram post, then hand it to the `postonce` skill if the user wants it published or scheduled.

## Before writing

Get or infer: the account (brand, creator, local business), the format (single photo, carousel or Reel), what the media shows, the one thing the viewer should feel or do, and any fact or detail that makes it specific. Look at the photos or video if you can. Never invent numbers, results, prices or quotes.

## The first line

Instagram shows about one line of caption before "more", and less under a Reel. That line has to work on its own. Pick one pattern:

| Pattern | Example shape |
| --- | --- |
| Name the moment | "The 6am batch nobody sees." |
| Say the result | "Three ingredients. Ten minutes. No oven." |
| Contrarian | "You don't need a ring light to film Reels." |
| Point to the media | "Swipe to the last photo before you judge." (carousels) |
| Save-worthy promise | "The 5 settings I change on every new phone." |

Don't open with "Happy Monday", "New post!", the brand name, or a string of emojis. The caption's first line should add to the media, not describe it.

## Body and CTA

- Short paragraphs, one or two sentences each, with line breaks.
- Match length to the job. A strong photo or Reel can take one or two lines. A carousel or tutorial can take a longer caption with the steps or context. The hard limit is 2,200 characters.
- Write like the account talks. Plain words, no "elevate", "unlock", "game-changer".
- End with one CTA that fits the post: save it, send it to someone, comment a specific answer, or tap the link in bio. One ask, not four.
- Links in captions aren't clickable on Instagram. Say "link in bio" if there's a link.

## Hashtags

Use 3 to 5 specific hashtags that describe the post's topic and audience, placed at the end. Skip broad tags like #love or #instagood. Instagram's own guidance favors a few relevant tags over many. PostOnce removes any hashtags past 30. For a researched set, use the `instagram-hashtag-generator` skill.

## Alt text

Write one short alt text line per image, usually one sentence: what's in the image, plus any text shown on it. The API doesn't set alt text, so tell the user to add it in the Instagram app (Edit post, then Edit alt text) once the post is live.

## Output

Give the caption exactly as it will appear, then hashtags on their own line, then alt text per image. Offer two alternative first lines if the user wants options. Offer to publish or schedule it with the `postonce` skill; confirm the Instagram account and the time before calling `create_post`. Instagram needs at least one photo or video, so check media exists first.
