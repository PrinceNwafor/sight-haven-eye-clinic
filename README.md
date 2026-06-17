# Sight Haven Eye Clinic — Website (Preview Demo)

A mobile-first, production-ready demo website for **Sight Haven Eye Clinic**, an eye clinic in
**Abuja**. Built with plain **HTML + CSS + vanilla JavaScript** — no build step, no dependencies.
Just open it in a browser and it works.

> This is a **preview/demo** the clinic can review, own, and customise. All copy, photos, prices,
> HMO list, doctor names and contact details are placeholders that are easy to replace.

---

## ▶️ Run it locally

No build needed. Either:

**Option A — open directly**
Double-click `index.html`. (Videos and the map embed work best over a local server, see B.)

**Option B — run a tiny local server (recommended)**
```bash
# from inside this folder:
python -m http.server 8000
# then visit:
#   http://localhost:8000
```
Or with Node:
```bash
npx serve .
```

## 🏗️ "Build"
There is **no build command** — it's a static site. The files you edit are the files that ship.
To deploy, just upload the folder to any static host (GitHub Pages, Netlify, Vercel, cPanel, etc.).

---

## 🎨 Where to replace the logo & assets

| Asset | File to replace (keep the same name) |
|-------|--------------------------------------|
| **Logo** (header, footer, favicon) | `assets/logo/sight-haven-logo.jpg` |
| Hero / eye-test photo | `assets/img/eye-test.webp` |
| Showroom / team / gallery photos | `assets/img/*.jpg` (see filenames) |
| Education videos (glaucoma, tonometry) | `assets/video/*.mp4` |
| Hero background video | `assets/video/eyecare-promo.mp4` |

Drop a new file in with the **same filename** and it appears automatically. To add new gallery
images, copy them into `assets/img/` and add a `<div class="gallery__item">…</div>` in the
**Gallery** section of `index.html`.

> Tip: A transparent **PNG logo** will look cleaner in the header/footer than the current JPG
> (which has a paper background). Save it as `sight-haven-logo.png` and update the few
> `src="assets/logo/sight-haven-logo.jpg"` references.

---

## ✏️ What to edit before going live (all clearly marked)

Search the HTML for these and replace:

- **Phone:** `+2348030000000` / `+234 803 000 0000`
- **WhatsApp:** the number `2348030000000` (also in `js/main.js` → `CLINIC_WHATSAPP`)
- **Email:** `sighthaveneyeclinic@gmail.com`
- **Instagram:** `instagram.com/sighthaveneyeclinic`
- **Address:** `Suite 00, [Street Name], Wuse 2, Abuja, FCT`
- **Map:** the `iframe` `src` in the **Location** section — set it to your exact address
- **Opening hours:** the Location section, the footer, and `HOURS` in `js/main.js`
- **Prices:** the "Indicative Prices" card in `index.html` (`₦00,000`)
- **HMO partners:** the "HMO & Insurance" section (`HMO Partner 1…6`)
- **Doctor names:** `book-appointment.html` step 2
- **Testimonials & stats:** sample content — swap for real reviews/numbers

## 🎨 Re-theming (colours)
All brand colours are CSS variables at the top of `css/style.css` (`:root { … }`). They were
derived from the Sight Haven logo (deep teal, vision cyan, brand cream). Change them in one place
and the whole site updates.

---

## 📁 Structure
```
sight-haven-eye-clinic/
├── index.html              One-page site: hero, services, eye-care education,
│                           family care, gallery, HMO, testimonials, map+hours, FAQ
├── book-appointment.html   5-step eye-test booking wizard (+ WhatsApp confirm)
├── css/style.css           Design system (brand tokens + components)
├── js/main.js              Nav, reveal, accordion, counters, booking engine,
│                           opening-hours status, WhatsApp confirmation
└── assets/
    ├── logo/               Clinic logo (also used as favicon)
    ├── img/                Photos (clinic, team, eyewear, screening)
    └── video/             Education + promo videos
```

## 📱 Notes
- **Mobile-first** and tuned so there is **no horizontal scroll / no side gaps** when you swipe.
- The booking form is **front-end only** — it shows a success screen and a pre-filled
  WhatsApp message. To take real bookings, POST the `state` object in `initBooking()`
  (`js/main.js`) to your backend or scheduling tool.
- SEO title/description are set around **"Eye clinic in Abuja"**, with Open Graph tags and
  LocalBusiness structured data.
