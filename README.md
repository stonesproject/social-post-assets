# social-post-assets

Public image host for automated social media posts.

**This repository is deliberately public.** The Instagram Graph API does not accept an
uploaded file — it takes an `image_url` and fetches it itself — so images destined for
Instagram have to sit behind a publicly readable URL. `raw.githubusercontent.com` on a
public repo gives exactly that:

    https://raw.githubusercontent.com/stonesproject/social-post-assets/main/posts/<file>.jpg

Images land here via the "Social Media Post Factory" workflow in n8n, which is fed by
Post Station (a local drag-and-drop page). Facebook and LinkedIn get the binary directly
and do not depend on this repo.

## Layout

    posts/YYYY-MM-DD-<ref>.jpg     one file per post that carried an image

## Housekeeping

Git keeps every version of every file forever, so this repo grows by roughly the size of
each image (~250 KB after Post Station resizes it). Deleting a file from `posts/` does not
reclaim the space — once a post is live, Instagram has already cached the image, so old
files can be pruned from the working tree whenever it becomes untidy. History rewriting is
not worth it.

Nothing here is confidential: only images that are being published publicly anyway.
Do not commit anything else to this repo.
