# SalatTimes background photos

Mosque photographs shown behind the Adhan screen in
[SalatTimes](https://github.com/IslamAlorabI/SalatTimes).

They are **not** bundled in the app. The app ships only a small `catalog.json`
listing what exists here, and downloads a photo when the user picks one.

## Layout

    full/<id>.webp     1080x1920, the background itself
    thumb/<id>.webp    360x640, shown in the picker grid

Both folders use the same `<id>`. `id` is what the app saves in its settings, so
**never rename or delete an existing file** — a user who picked it would lose
their background. Adding new photos is safe.

## Rules for adding a photo

1. **Sunni mosques only.**
2. **No identifiable people**, and in particular no women. Distant, unidentifiable
   figures are the most that should ever appear; crop them out where you can.
3. It must be a mosque — not a shrine, mausoleum, or tomb complex.
4. Crop to 9:16, resize to 1080x1920, save as WebP quality 82; make a 360x640
   thumbnail at quality 78.
5. Add a row to `catalog.json` in the app and to `CREDITS.md` here.
6. Prefer a calm, uncluttered upper third — the prayer name is drawn over it.

## Licence

Per photo. See [CREDITS.md](CREDITS.md).
