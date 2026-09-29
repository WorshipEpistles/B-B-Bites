# B&B Bites

Marketing and pre-order site for B&B Bites — authentic Ugandan fast food, catering, events management and training. Opening soon in Entebbe, Uganda.

## Running locally

`index.html` is a single self-contained page with no build step. Open it directly in a browser, or serve it:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Editing the menu

Menu items live in the `MENU_ITEMS` array near the bottom of `index.html` and are rendered into both the menu grid and the footer list. To change a price or add a dish, edit one entry:

```js
{ id: 'kikomando', name: 'Kikomando', price: 5000, description: '...', image: 'zkfcnwdhnnfqglrnwig8.jpg' }
```

`price` is in Ugandan Shillings and includes VAT; delivery is charged separately. `image` is a filename appended to `IMAGE_BASE`.

## Ordering

There is no backend. "Add to Order" builds a cart in the page, and the order bar hands the itemised order to WhatsApp on `WHATSAPP_NUMBER` (+256 777 213513). The contact form does the same. Payment is Mobile Money or cash, arranged over WhatsApp.

## Deploying

Recommended: Cloudflare Pages (free tier, fast in East Africa).

1. Sign in at https://dash.cloudflare.com and go to Workers & Pages > Create > Pages > Connect to Git.
2. Select this repository. Leave the build command empty and set the output directory to `/`.
3. Deploy. Every push to `main` redeploys automatically.
4. Add the custom domain under the project's Custom domains tab once the domain is registered.

Netlify and GitHub Pages work the same way for a static site.

## Before launch

- Replace the placeholder canonical/Open Graph domain in `<head>` with the real domain.
- Add the street address to the contact section and to the `Restaurant` JSON-LD, and re-add a Google Maps embed pointing at the Google Business Profile listing.
- Add real social media links once the pages exist.
- Move images off the Hugging Face Space into this repo, converted to WebP.
