# Sonja — artist's gallery and shop

**Live site: [zakariansonja.com](https://zakariansonja.com)**

A portfolio and online shop for Sonja, an artist based in Marseille. It sells original artworks (unique pieces) and hand-painted merch (T-shirts, tote bags). The site is available in French, English and Russian, with Stripe payments and a private admin area.

## Stack

Next.js 16 (App Router), React 19, TypeScript, Tailwind CSS 4, PostgreSQL + Prisma 7, Stripe, Nodemailer, Sharp.

## Public site

- **Home**: a photo of a gallery wall with artworks, paper notes and inscriptions placed on it. The layout is set in the admin area.
- **Works catalog**: paginated (18 per page), with filters for availability, technique, size and price, plus four sort orders. Filters are kept in the URL.
- **Artwork page**: images, details, price with VAT, shipping cost and a buy button. Sold works stay visible with a "Vendu" ribbon.
- **Shop**: merch with sizes and stock, which can be bought directly or added to the cart.
- **Cart**: a side drawer plus a cart page, saved in the browser's localStorage.
- **About, Contact**: the contact form emails the artist and is rate-limited.
- **Legal**: mentions légales, CGV, privacy policy, withdrawal form and a GDPR cookie banner.
- **SEO**: localized metadata with hreflang, Product JSON-LD, sitemap, robots.txt and Open Graph.

## Checkout

1. The buyer enters a delivery address on the site, and shipping is priced by zone (France / EU / world).
2. Payment happens on Stripe's hosted Checkout page.
3. The Stripe webhook creates the order, marks unique artworks as sold, lowers merch stock and sends emails.
4. A full refund in Stripe marks the order as refunded and puts the items back on sale.

Prices are stored in euro cents and include VAT: 5.5% for artworks, 20% for merch. Order emails go out in the buyer's language.

## Languages

Every route has a locale prefix (`/fr`, `/en`, `/ru`). On a first visit the locale is picked from a cookie, then Accept-Language, and remembered after that. Artwork and merch titles, descriptions and slugs are stored per language.

## Admin

Protected by a password and a JWT session cookie, with login rate limiting.

- **Works / Shop**: create and edit artworks and merch (text in three languages, price, status, images).
- **Wall**: drag-and-drop ordering of the catalog.
- **Home page**: a visual editor for the hero wall layout.
- **Orders**: payment and fulfillment status, plus tracking numbers.

Uploaded images are converted to WebP in three sizes (300 / 800 / 2000 px), along with a blur placeholder.
