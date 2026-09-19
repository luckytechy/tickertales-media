# tickertales-media

Public image host for [Ticker Tales](https://www.tickertales.in) social posts.

This repo exists for one reason: **Buffer's API has no upload endpoint.** You
host the image yourself and hand Buffer a public URL, which it fetches
anonymously at publish time - often days after the post was scheduled. A private
repo's raw URLs need a token, so Buffer cannot read them. Hence: public, and
nothing in here but rendered images.

The agent that writes here lives in `luckytechy/tickertales` (private).

## Layout

```
social/<pillar>/<YYYY-MM-DD>-<slug>-<platform>-<n>.png
```

Served from:

```
https://raw.githubusercontent.com/luckytechy/tickertales-media/main/<path>
```

## Rules

- **Nothing but images.** No drafts, no config, no keys, no notes. Assume every
  byte here is world-readable forever.
- **Never delete an image for a post that has not published yet.** Buffer
  resolves the URL when the post goes out, not when it is queued. Pulling a file
  early makes the post fail silently.
- Files older than 60 days are pruned automatically - by then every post
  referencing them has long since published.
