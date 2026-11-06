# শুভঙ্কর ও প্রীতি — Digital Wedding Card

A mobile-first animated wedding invitation in ivory, gold and maroon. It is a single static page with no build step.

- Opens with a sealed envelope. Tapping it breaks the wax seal, lifts the flap, slides the card out and drops a shower of petals.
- Sections: cover → invitation letter → groom & bride → dates and countdown → photos → venue and directions → contact.
- Has a Bengali / English switch.
- Includes a WhatsApp preview image (`images/og-cover.jpg`).

## 1. Add your photos

Put these files in the `images/` folder. Use exactly these names:

| File | What |
| --- | --- |
| `images/groom-portrait.webp` | Groom portrait (already added) |
| `images/bride-portrait.webp` | Bride portrait (already added) |
| `images/couple-1.jpg` … `images/couple-5.jpg` | Photos of you together (4–5) |

Tips:
- The portraits sit in a gold arch on maroon velvet, with a halo behind the head. A cut-out (transparent PNG or WebP) looks best. An ordinary vertical photo also works: it fills the arch, so keep the face in the upper half. To use a different file, change `photos.groom` / `photos.bride` in `CONFIG`.
- If a face sits too high or too low in its arch, adjust `--hy` (halo height), `--ps` (zoom) and `--py` (shift down) on that portrait in `index.html`.
- Resize each photo to about **1200 px** on the long side, under **400 KB**. You can use https://squoosh.app. This keeps the card fast on mobile data.
- If a photo is missing, the card still looks finished. A missing portrait shows a gold monogram, and the photo section stays hidden until at least one couple photo exists.
- Using `.jpeg`, `.png` or `.webp`, or only 4 couple photos? Edit the `photos` list in `CONFIG` near the bottom of `index.html`.

## 2. Deploy on Vercel

1. Push this repo to GitHub.
2. On https://vercel.com, click **Add New → Project** and import the repo.
3. Framework preset: **Other**. Build command: none. Output directory: leave it as is.
4. Click **Deploy**.

**WhatsApp preview picture:** the `og:url`, `og:image` and `twitter:image` lines in `index.html` already point to `https://digital-card-one-lyart.vercel.app`. If the site address ever changes, update those lines; WhatsApp needs the full address. WhatsApp remembers links, so after changing the preview, test with something new on the end, e.g. `/?v=3`.

## 3. Sharing links

| Link | What guests see |
| --- | --- |
| `https://YOUR-SITE.vercel.app/` | Bengali card |
| `https://YOUR-SITE.vercel.app/?lang=en` | Opens in English |
| `https://YOUR-SITE.vercel.app/?to=মিত্র পরিবার` | Envelope addressed to "মিত্র পরিবার" |
| `https://YOUR-SITE.vercel.app/?to=Mitra Family&lang=en` | Addressed + English |

## 4. Changing details

All contact, map, date and photo settings are in the `CONFIG` block near the bottom of `index.html`:

- `phone`, `whatsapp`: currently 9836937295
- `mapsUrl`: your Google Maps link for Sudhakunja
- `mapEmbed` (optional): to show a live map instead of the illustrated one, open the place in Google Maps → **Share → Embed a map**, and paste only the `src="…"` link
- `music`: background music, currently `audio/reception-music.mp3`. It fades in when the envelope opens, pauses while the guest is in another app, and the round music button mutes it. To change it, put a new mp3 in `audio/` and update this line; set it to `""` for no music.

The invitation wording is plain HTML in `index.html`. Search for the text you want to change.
