# Buying Signal Bot

A bot that watches X for people leaving their tools, finds out who they are, and hands you a short list every morning.

**Grok Bot** does the watching. **FullEnrich** turns a profile into a person you can qualify and contact.

Setup takes about twenty minutes. After that it runs on its own.

---

## 1. Grok Bot

- Create a new bot in Grok Bot, or open an existing one.
- Connect the **X plugin** and sign in once.
- Check your **X API credit balance** before running a big search. This is the step people forget, and the search silently returns nothing without it.
- Optional: name it something you will recognise in the sidebar. *Buying Signal Bot* works.

## 2. FullEnrich

- Create an account at fullenrich.com and generate an **API key**.
- Put the key somewhere the bot can read it. On the Grok Bot machine: `/home/box/.config/fullenrich/api_key`
- **What it costs:** a people lookup is about **0.25 credit** when a person is found. A work email is about **1 credit** when found. Nothing is charged when nothing is found.
- **The rule that keeps this cheap:** never enrich a post until it has survived the filters. Enrichment is the last step, not the first.

---

## 3. What you have to tell it

| Input | Example | Why it matters |
|---|---|---|
| **Tools to watch** | Clay, Apollo, ZoomInfo, your three closest competitors | Exact product names. A vague topic returns noise. |
| **Pain sentences** | *looking for an alternative* · *switching from* · *moving off* · *we cancelled* · *too expensive* · *the data is bad* | The words are the whole filter. Words are intent, topics are noise. |
| **Buyer gate** | Company 11 to 1000 people · founder, C-level, VP or Director | Who can actually sign. Everything else gets dropped. |
| **Schedule** | Every day at 7:00 in your timezone, last 24 hours only | Freshness is the value. A three-week-old complaint is already answered. |
| **Output** | A table. No outreach, ever. | Person, company, quote, link, opening line, and the email if you asked for it. |

---

## 4. What it does every morning

1. Searches X over the last 24 hours, using your sentences and your tool names.
2. Drops the memes, the jokes, the quote tweets and the promo posts.
3. On the survivors: reads the bio to find a LinkedIn link, or a name and a company.
4. Runs the FullEnrich lookup: who they are, the company, its size, their role.
5. Drops wrong size and wrong role, and tells you how many it dropped.
6. Only then, and only on the keepers, pulls the work email if you asked for it.
7. Delivers the table in the chat. It sends nothing to anyone, ever.

## 5. What you get back

One card per keeper:

> **Name** · handle · role · company · size · email (if enriched)
> what they actually wrote · link to the post
> one opening line, built only on their own words
> keep or drop, with the reason

---

## 6. Reality check, from the real runs

This is measured, not assumed. Run it on your own category before you trust it.

| Market | Posts scanned | Real signals |
|---|---|---|
| Developer tools | 15 | 8 |
| AI tools | 15 | 6 |
| CRMs | 25 | 2 |
| Marketing tools | 15 | 2 |
| Sales and data tools | 25 | 0 |

People who build software announce their moves in public, with the price and the reason. Nobody posts that their company is changing data provider.

**Three things that will save you money:**

- If your buyers are in the quiet half, keep this exact setup and point the watch somewhere else: review sites, forums, and the job ads they post three months later to fix the problem themselves.
- A thin X bio with no LinkedIn and no company means skip. Do not burn a credit on a guess.
- The drop count is the most useful number in the routine. Keeping almost everybody means your words are too wide. Dropping everybody means your competitor list is wrong.

---

## The rule to set on day one

Require your approval for anything that leaves the room: a message, a reply, a post.

The bot drafts. You sign.

---

Built by Yonathan Cohen · [Tool Monsters](https://toolmonsters.com) · hello@toolmonsters.com
