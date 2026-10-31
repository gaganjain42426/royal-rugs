# Royal Rugs

Enquiry-only website for Royal Rugs — a hand-knotted carpet and rug house.
Thirty catalogue pieces, a filterable collection, per-rug enquiry pages and a
custom-size enquiry builder. There is no cart and no checkout: every piece is
quoted individually, because size, material and colourway all move the price.

Static site. No build step, no dependencies, no framework — one HTML file plus
images. Open `index.html` in a browser and it runs.

## Layout

```
index.html          the entire site: markup, styles and script
img/
  r01–r30.jpg       the 30 catalogue pieces
  banner-*.jpg      hero and section banner photography
  logo-mark.png     the "R" monogram
  logo-lockup.png   full logo with wordmark
```

Navigation is hash-based and client-side (`#collection`, `#custom`, `#r08`, …),
so any static host will serve it correctly with no redirect rules.

## Before launch

### 1. Fill in the contact details

Near the top of the `<script>` block in `index.html`:

```js
var CONFIG = {
  businessName: 'Royal Rugs',
  whatsapp: '',                 // digits only, with country code, e.g. '919876543210'
  email: '[YOUR EMAIL]',
  phone: '[YOUR PHONE]',
  address: '[YOUR SHOWROOM ADDRESS]'
};
```

Set `whatsapp` and every enquiry panel gains a one-tap **Send on WhatsApp**
button with the enquiry pre-filled. Until then the panels show the composed
message with a copy button.

### 2. Replace the remaining placeholders

Search `index.html` for `[` to find them all:

| Placeholder | Where |
|---|---|
| `[YEAR]` | hero eyebrow, footer copyright |
| `[YOUR REGION]`, `[YOUR MARKETS]` | the craft section |
| `[YOUR LEAD TIME]` | every rug's spec table |
| `[YOUR OPENING HOURS]` | contact page |
| `[QUALITY TBC]` | the three traditional rugs — knot quality was not printed on their catalogue sheets |
| `[C.NO TBC]` | the same three pieces |

### 3. Photography

**The banner images are AI-generated mood photography.** The rugs in those
scenes are not catalogue pieces and are deliberately not labelled as specific
products anywhere on the site. Replace them with real photography when it is
shot. Keep that separation intact: banners carry atmosphere, the catalogue
plates carry the real product.

Each rug page also reserves three empty photo slots — detail shot, room
setting, and knot/back — which still need shooting.

## Catalogue data

The 30 pieces live in the `RUGS` array in `index.html`. Design numbers, C.
numbers, sizes in feet and metres, and knot quality are transcribed from the
supplier catalogue sheets and are accurate. **Rug names** (Glacier, Nightfall,
Lagoon…) are editorial — rename freely.

To add a piece: drop the image in `img/`, add an entry to `RUGS`, and it
appears in the collection, the filters and the search automatically.

## Hosting

Any static host works. The repo root is the site root — no build command and
no output directory to configure.
