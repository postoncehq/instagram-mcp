---
name: instagram-hashtag-generator
description: Pick a small set of specific, relevant Instagram hashtags for one post, carousel or Reel, sized from broad to niche. Use when the user asks for Instagram hashtags, a hashtag generator, which hashtags to use, or to clean up a long hashtag block before posting with the PostOnce Instagram MCP.
metadata:
  author: PostOnce
  version: "0.1.0"
---

# Instagram hashtag generator

Hashtags on Instagram help it understand what a post is about and who it's for. They're a label, not a reach hack. A few precise tags beat a block of 30 generic ones, and Instagram's own creator guidance recommends a handful of relevant tags.

## Before choosing

Get or infer: what the post shows, the topic, the audience (who should find it), the account's niche, and the location if it matters (local business, event, travel). Read the caption if there is one.

## How to pick

Choose 3 to 5 tags, one or two from each layer:

| Layer | What it is | Example for a sourdough Reel |
| --- | --- | --- |
| Topic | What the post is about | #sourdough |
| Niche | The specific angle or audience | #sourdoughforbeginners |
| Context | Place, format, event or community | #londonbakers |
| Brand (optional) | The account's own tag, if it uses one consistently | #mayabakes |

Rules:
- Every tag must describe this post. A tag the post doesn't match sends it to the wrong people.
- Skip broad, meaningless tags: #love, #instagood, #photooftheday, #viral, #explore, #fyp.
- Skip banned or spammy-looking tags and long strings of near-duplicates (#food #foodie #foodporn #foodlover).
- Prefer the words people search in plain English. Instagram search also reads the caption and keywords, so a clear caption does more than extra tags.
- Check spelling and that the tag is in normal use; don't invent tags unless it's the user's brand tag.
- Put tags at the end of the caption, on their own line. Don't put them in the first line.

## Cleaning up an existing block

If the user has a long list, keep the 3 to 5 that best match the post and explain in one line why the rest were cut. PostOnce drops any hashtags past 30 automatically, so a longer list won't all publish.

## Output

Return the recommended set on one line, ready to paste, then one short line per tag on why it fits. Offer one alternate set for a different audience if useful. If the user has the caption and media ready, offer to add the tags and publish or schedule with the `postonce` skill; confirm the Instagram account and the time before calling `create_post`.
