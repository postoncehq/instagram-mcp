---
name: instagram-bio-generator
description: Write Instagram bio options (150 characters), a searchable name field and a link-in-bio line for a creator, brand or business profile. Use when the user asks for an Instagram bio, bio ideas, an Instagram bio generator, or to rewrite or improve their Instagram profile text.
metadata:
  author: PostOnce
  version: "0.1.0"
---

# Instagram bio generator

Write profile text the user pastes into Instagram themselves. This MCP publishes posts; it doesn't edit profiles.

## Before writing

Get or infer: who the account is for, what they get from following, what makes it different, the main action (shop, book, join, download, watch), and where the link goes. Ask for proof worth showing: a real credential, a follower-facing result, a location for a local business. Never invent numbers, awards or press.

## The parts

| Field | Limit | Job |
| --- | --- | --- |
| Name | 64 characters | Shown in bold and searchable. Add a keyword after the name: "Maya Chen · Sourdough Recipes". |
| Username | 30 characters | Only suggest a change if the user asks. |
| Bio | 150 characters | Who it's for, what they get, why trust it, what to do next. |
| Link | Set in the app | One link or several; say where it goes in the bio's last line. |

## How to write the bio

- Line 1: the promise to the follower, not a job title. "Weeknight dinners in 20 minutes" beats "Food blogger".
- Line 2: proof or personality: a credential, a place, a real number, a point of view.
- Line 3: the next step, pointing at the link. "New recipe every Tuesday ↓"
- Use line breaks. One or two emojis are fine as markers; don't use them as decoration on every line.
- Skip hashtags and filler like "living my best life", "passionate about", "welcome to my page".
- For a business, include the city if customers visit in person.

## Output

Give 3 bio options in different directions (clear and direct, personality-led, proof-led), each with its character count, plus 2 name field options. Mark the one you'd pick and why in one line. Tell the user to paste it in Instagram under Edit profile. If they also want a post announcing a rebrand or new link, write it with the `instagram-caption-generator` skill and offer to publish it with the `postonce` skill.
