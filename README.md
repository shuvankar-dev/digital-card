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
| `images/groom-cutout.webp` | Groom portrait with the background removed (already added) |
| `images/bride-cutout.webp` | Bride portrait with the background removed (already added) |
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

**After the first deploy**, open `index.html` and change the `og:image` line to your full site address, e.g.
`<meta property="og:image" content="https://YOUR-SITE.vercel.app/images/og-cover.jpg">`.
WhatsApp needs the full URL to show the preview picture when you share the link.

## 3. Sharing links

| Link | What guests see |
| --- | --- |
| `https://YOUR-SITE.vercel.app/` | Bengali card |
| `https://YOUR-SITE.vercel.app/?lang=en` | Opens in English |
| `https://YOUR-SITE.vercel.app/?to=মিত্র পরিবার` | Envelope addressed to "মিত্র পরিবার" |
| `https://YOUR-SITE.vercel.app/?to=Mitra Family&lang=en` | Addressed + English |

## 4. Changing details

All contact, map, date and photo settings are in the `CONFIG` block near the bottom of `index.html`:

- `phone`, `whatsapp`: currently 7630955747
- `mapsUrl`: your Google Maps link for Sudhakunja
- `mapEmbed` (optional): to show a live map instead of the illustrated one, open the place in Google Maps → **Share → Embed a map**, and paste only the `src="…"` link
- `music` (optional): add a shehnai mp3, e.g. `audio/shehnai.mp3`. It starts playing when the envelope opens, and a small music button appears.

The invitation wording is plain HTML in `index.html`. Search for the text you want to change.
