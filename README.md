# Sonja — artist's gallery and shop

Website of Sonja, an artist based in Marseille, France. Her work is expressive and close to art brut. She works in India ink, pen, pencil, acrylic and gouache, on paper, canvas and plywood. Visitors can browse and buy her original works, along with hand-painted merch: tote bags and T-shirts.

The site is available in three languages (French, English, Russian). It takes payments online, works out shipping and VAT on its own, and sends emails to both the buyer and the artist. Sonja manages all of the content herself through a private admin area.

---

## Visual concept

The site is designed as a dark exhibition room. The works hang on a wall in frames under spot lighting, with paper notes pinned beside them that give the title and price. The interface stays in the shadows so the paintings carry the screen.

- **Dark palette** with warm brass accents. Serif typefaces (Cormorant Garamond, EB Garamond), plus a clean sans-serif (Inter) for small labels.
- **Several frame types**: gilt, wood and mat. Each frame follows the real proportions of the painting.
- **Paper notes** beside the works, either horizontal or vertical.
- **"Vendu" ribbon** on sold works. Sold pieces don't disappear from the site; they stay on as part of the portfolio.
- **Responsive layout**: the display adapts to phones, tablets and large monitors.

---

## Pages

### Home
The opening screen is a photograph of the studio wall, hung with works, handwritten inscriptions and a text block. Sonja decides where each work hangs on the wall, how large it is, its angle and where its note sits. She does this in a visual editor in the admin area (see below). Below the opening screen are sections about the artist, the studio and the merch, plus a newsletter sign-up.

### Works catalog (Œuvres)
The full collection, 18 works per page, with filters for:
- **availability**: all, for sale, sold;
- **technique**: painting, India ink, pen, mixed media;
- **size**, by the longest side: under 35 cm, 35–65 cm, 65 cm and up;
- **budget**: under €500, €500–1,000, €1,000–2,000, over €2,000.

There are four sort orders: "Curated" (the order chosen by the artist), "Newest", "Price: low to high" and "Price: high to low". Filters are saved in the page address, so a selection can be shared as a link. On phones the filters open in a slide-out panel, and the active filters and number of results are shown above the list.

### Artwork page
Large images, title, year, technique, surface, dimensions, whether the work is framed and comes with a certificate of authenticity, plus a description and the story behind the piece. The page also shows the price including VAT, the shipping cost and an "Acquérir" (buy) button. When a work is sold or reserved, the page says so.

### Shop (Boutique)
The merch catalog: T-shirts and tote bags. Each product page has a photo gallery, size selection that takes stock into account, the material, and how the piece was made (unique hand-painted piece, limited edition, small series). Items can be bought straight away or added to the cart.

### Cart
The cart opens as a side panel from any page, and also has its own page. Shoppers can change quantities and remove items, and the total updates straight away. The cart's contents stay in the browser between visits.

### About, Contact
The artist's biography, with photos of the studio and her working process. The contact form sends messages to the artist by email. Field checks and a limit on how often the form can be sent protect it from spam.

### Legal pages
The set of pages an online shop in France must have:
- Mentions légales (legal notice);
- CGV (terms of sale);
- Politique de confidentialité (privacy policy, GDPR);
- withdrawal form (formulaire de rétractation).

There is also a GDPR cookie consent banner.

---

## Buying and payment

1. The buyer clicks "Acquérir" on a work or checks out the cart.
2. On the **delivery** page they enter their address and choose a country. The shipping cost appears right away.
3. Payment happens on a secure **Stripe** page.
4. Stripe tells the site the payment went through. The site creates the order, marks a unique work as sold, lowers the merch stock and sends the emails.
5. The buyer lands on a **"Merci"** page showing the order number and contents. The items just bought are taken out of the cart, and anything else stays in it.

### Shipping
The world is split into three zones: **France**, **the European Union** and **the rest of the world**. The rate depends on the zone and on what the order contains: a painting, merch, or both. Each order records the shipping amount the buyer actually paid.

### VAT
Prices on the site include VAT. The rate depends on the type of item: **5.5%** for artworks and **20%** for merch. The VAT amount is worked out for each order separately and saved with it.

### Refunds
When a full refund is issued in Stripe, the order is marked "refunded", the works go back on sale and the buyer receives a cancellation email.

### Emails
The site sends emails in the language the buyer used to place the order (French, English or Russian):
- to the buyer: order confirmation;
- to the artist: sale notification with the delivery address;
- to the buyer: cancellation and refund notice;
- to the artist: messages from the contact form.

---

## Languages

- All content is available in **French, English and Russian**. Every work and every product has a title, a description and a page address in all three languages.
- On a first visit the language is picked from the browser settings. After that the site remembers the visitor's choice.
- The language can be changed from the header. The visitor stays on the same page, just in the other language.

---

## Admin area

A private area for the artist. Access is by password, the session is kept in a secure cookie, and password guessing is rate-limited.

- **Works**: add and edit paintings, with texts in three languages, technique, surface, year, dimensions, price, status (for sale, sold, hidden), frame type and photo uploads.
- **Wall**: the order of works in the catalog. Cards are dragged with the mouse, including across pages, and the artist can see straight away how the display will look.
- **Home page**: a visual editor for the opening screen. Works, notes, handwritten inscriptions and the text block are dragged across the wall photo, and can be scaled and rotated. The editor shows which part of the photo will be visible on different screen sizes.
- **Shop**: manage the merch, meaning prices, sizes, stock, photos and descriptions.
- **Orders**: a list of orders with their contents, address, amounts, payment status and shipping status ("pending", "shipped", "delivered"). A tracking number can be added.

The site compresses uploaded photos, converts them to a modern format and saves them in several sizes: for thumbnails, cards and full-screen viewing. While a photo loads, a blurred preview takes its place.

---

## Search and social media

- Each page gets a title and description for search engines in its own language, and search engines are told that it has versions in the other languages.
- Works and products are marked up as products with a price and availability, so Google can show a rich result for them.
- The site has a sitemap and a robots.txt.
- Links shared in messaging apps or on social media appear with an image and a description.

---

## Technology

- **Next.js 16** and **React 19**, **TypeScript**
- **Tailwind CSS 4**
- **PostgreSQL** and **Prisma 7**
- **Stripe**: payments and refunds
- **Nodemailer**: email
- **Sharp**: image processing
