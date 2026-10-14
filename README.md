# snapgrid-assets

Remote content for the **Snapgrid – Photo Collage** Android app (`com.nnastudio.collage.maker`):
templates, fonts, frames, borders and stickers. Served free through jsDelivr:

```
https://cdn.jsdelivr.net/gh/anhngocnguyen1034/snapgrid-assets@main/<folder>/manifest.json
```

| Folder | Manifest | Files |
|---|---|---|
| `templates/` | categories → templates (`thumbnail`, `overlay`, `cells`, `photoCount`, `aspectRatio`) | `<category>/pr_N.webp` (preview), `<category>/N.webp` (overlay) |
| `fonts/` | `fonts[].files` | `fonts/*.ttf` |
| `frames/`, `borders/` | `frames[]` / `borders[]` with `id`, `url` | `frames/frames/*.webp`, `borders/borders/*.webp` |
| `stickers/` | `albums[]` with `icon` and `stickers[].url` | `stickers/albums/<album>/*.webp` |

## Adding content

1. Add the files, then the entry in the folder's `manifest.json` (paths are relative to its `baseUrl`).
2. Bump `version` in that manifest.
3. Push to `main`, then purge the CDN cache so devices see it right away
   (otherwise jsDelivr refreshes `@main` within ~12 h):

```
curl https://purge.jsdelivr.net/gh/anhngocnguyen1034/snapgrid-assets@main/templates/manifest.json
```

The app also caches each manifest for 1 hour.
