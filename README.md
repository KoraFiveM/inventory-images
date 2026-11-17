# inventory-images

Item artwork for [kora_inventory](https://github.com/KoraFiveM/kora_inventory).

Every file in `inventory/` is served at

```
https://cdn.koraframe.work/inventory/<name>.webp
```

(which redirects to jsDelivr, a free open-source CDN backed by this repo). The item name in your item list is the file name:
an item called `lockpick` uses `inventory/lockpick.webp`.

## Adding or changing images

Two ways, both end up as a pull request:

1. **On the website** (easiest): sign in at <https://koraframe.work/admin/uploads>, drop in one image or a whole folder, and
   submit. Images that do not fit the spec can be converted in the browser first. The site opens the pull request for you.
2. **Directly on GitHub**: fork, add files to `inventory/`, open a pull request.

Every pull request is checked automatically by the `image-spec` check. It must be green before anything is merged.

## The spec

| Rule | Value |
|---|---|
| Format | WebP |
| Size | exactly 100 × 100 px |
| Resolution | 300 DPI (EXIF `XResolution` / `YResolution`, unit inch) |
| Transparent border | the outer 10 px must be fully transparent (alpha 0) |
| File size | at most 200 KB |
| File name | `a-z`, `0-9`, `_` and `-` only, at most 80 characters, plus `.webp` |
| Location | `inventory/` only. Nothing else in a pull request may change |

Replacing or deleting an existing image is allowed but always needs a maintainer to review it.

The source of truth for these numbers is `src/lib/images/webp.ts` in the website repository. If this table and the check
ever disagree, the check wins and this file is wrong. Please open an issue.

## Browsing

Open the [`inventory/`](./inventory) folder. GitHub shows a preview for each file.
