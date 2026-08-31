# SalatTimes background photos

Mosque photographs shown behind the Adhan screen in
[SalatTimes](https://github.com/IslamAlorabI/SalatTimes).

The photos are **not** bundled in the app. The app reads `catalog.json` from
this repository and downloads a photo only when the user picks one, so the APK
stays small no matter how many photos live here.

**Adding a photo here is enough — it does not need a new app release.** The app
re-reads `catalog.json` from this repository every time the background picker is
opened, and caches it. Its own bundled copy of `catalog.json` is only a fallback,
used on an install that has never been online.

| Change made here | Reaches users without an app update? |
|---|---|
| Add a photo (both files + a `catalog.json` row) | Yes, next time they open the picker |
| Replace a photo, keeping the same file name | Yes, for anyone who has not downloaded it yet |
| Remove a photo's row from `catalog.json` | Yes, it stops being offered |
| **Rename or delete a file that is still listed** | **No — it breaks for whoever picked it** |

## Layout

    catalog.json       the list the app reads
    full/<id>.webp     1080x1920, the background itself
    thumb/<id>.webp    360x640, shown in the picker grid

`full/` and `thumb/` use the same `<id>`, and it must match the entry's `id` in
`catalog.json`. That `id` is what the app writes into the user's settings, so
**never rename or delete a file that is still listed**. Adding photos is safe.

The app ignores any entry whose `id` contains anything other than letters,
digits, `_` or `-`, or whose `fileName` contains `/`, `\` or `..`.

## Rules for adding a photo

1. **Sunni mosques only.**
2. **No identifiable people**, and in particular no women. Distant, unidentifiable
   figures are the most that should ever appear; crop them out where you can.
3. It must be a mosque — not a shrine, mausoleum, or tomb complex.
4. Crop to 9:16, resize to 1080x1920, save as WebP quality 82; make a 360x640
   thumbnail at quality 78.
5. Add a row to `catalog.json` **here**, and a credit line to `CREDITS.md`.
   `sizeBytes` and `thumbSizeBytes` must be the real byte sizes — the app shows
   them before downloading and uses them for the progress bar.
6. Prefer a calm, uncluttered upper third — the prayer name is drawn over it.

## Licence

Per photo. See [CREDITS.md](CREDITS.md).
