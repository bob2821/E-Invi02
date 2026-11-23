# Anirudh & Kaviya — interactive wedding invitation

A single-page invitation: a cord-tied envelope that unties on tap, then the invitation with a scratch-to-reveal date,
countdown, function cards, photo stack, an unrolling venue scroll, a press-and-hold heart burst and 3D wedding rings.

No build step. Everything the page needs is in this folder, except the fonts, which load from Google Fonts.

## Put it on GitHub Pages

1. Create a new **public** repository on GitHub (for example `wedding-invite`).
2. Upload **every file in this folder** to the repository root. There are no sub-folders: select all the files and drag them in together.
   On github.com: *Add file → Upload files*, drag the files in, then *Commit changes*.
3. Open *Settings → Pages*. Under *Build and deployment*, set **Source** to *Deploy from a branch*, **Branch** to `main` and folder to `/ (root)`. Save.
4. After a minute the site is live at `https://<your-username>.github.io/<repository-name>/`.

## Change the details

Open `index.html` and find the block that starts with `EDIT EVERYTHING HERE` (search for `const CONFIG`).
Names, date and time, venue, Google Maps link, each function, the closing line and the RSVP number are all there.

- **Date and time:** `ceremonyStart` / `ceremonyEnd` use the form `2027-02-14T07:30:00+05:30`.
- **Venue link:** paste the venue's Google Maps link into `mapsUrl`.
- **RSVP button:** put a WhatsApp number in `rsvpWhatsApp` in international format without `+` (for example `919876543210`). Leave it empty to hide the button.

## Add real photos

1. Upload the image files next to `index.html` (portrait, about 900 × 1200 px, under 400 KB each works well).
2. In `CONFIG.story`, set each `src` to the file name, for example `{ src: "photo1.jpg", caption: "The first hello" }`.

Frames with an empty `src` show a painted placeholder.

## Screens

- Phones: fills the screen at any size, portrait or landscape.
- Tablets and computers: shown as a centred phone-shaped column.
- Slow devices: the 3D scene lowers its resolution and effects automatically. Without WebGL the page still opens, with a simpler envelope.

## Credits

3D rendering uses three.js r128 (MIT licence, see `THREE-LICENSE.txt`).
