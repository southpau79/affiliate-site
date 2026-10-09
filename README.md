# Affiliate Site Starter (India)

A lightweight Astro product-deals website for India, designed for static hosting on Cloudflare Pages.

## Features

- Responsive product grid
- Search and category filters
- Manual product data in `src/data/products.js`
- INR pricing and merchant labels
- Affiliate disclosure
- Privacy page starter
- SEO metadata, sitemap and 404 page
- No database or API keys required

## 1. Run locally

Install Node.js (LTS), then run:

```bash
npm install
npm run dev
```

Open the local URL printed by Astro.

To test a production build:

```bash
npm run build
npm run preview
```

## 2. Add real products

Edit `src/data/products.js`. Each product uses this structure:

```js
{
  id: "unique-product-id",
  title: "Product title",
  merchant: "Merchant name",
  category: "Electronics",
  price: 2499,
  originalPrice: 3499,
  image: "https://example.com/product-image.jpg",
  affiliateUrl: "https://merchant.example/your-affiliate-link",
  badge: "Deal",
  description: "Short, accurate product description."
}
```

Use your own approved affiliate links and images you are permitted to use. Confirm current prices, availability, and affiliate-program rules before publishing. Do not imply that sample offers are live or verified.

Categories currently shown: Electronics, Home, Fashion, Beauty. Add a category to the category list in `src/pages/index.astro` if you introduce a new one.

## 3. Set your production domain

Edit `site` in `astro.config.mjs` to your actual canonical domain, for example:

```js
site: "https://deals.yourdomain.in"
```

Use the exact hostname you intend to publish on. Do not leave `example.com` in production.

## 4. Push to GitHub

Create an empty repository at https://github.com/new, for example `affiliate-site`.

From this project directory:

```bash
git init
git add .
git commit -m "Initial affiliate site starter"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/affiliate-site.git
git push -u origin main
```

Replace `YOUR-USERNAME` with your GitHub username. If Git says a remote already exists, inspect it with `git remote -v` before changing it.

## 5. Deploy on Cloudflare Pages

1. Sign in to https://dash.cloudflare.com/.
2. Open **Workers & Pages**.
3. Select **Create application** and choose the **Pages** option.
4. Choose **Import an existing Git repository** and connect GitHub if prompted.
5. Select `affiliate-site` and choose **Begin setup**.
6. Set:
   - Production branch: `main`
   - Framework preset: `Astro` (if offered)
   - Build command: `npm run build`
   - Build output directory: `dist`
7. Select **Save and Deploy**.

Cloudflare will install dependencies and build the project. After the first successful deployment, it will provide a `*.pages.dev` URL and rebuild on subsequent pushes to the production branch.

## 6. Connect your existing domain

In the Cloudflare Pages project:

1. Open **Custom domains**.
2. Select **Set up a custom domain**.
3. Enter the hostname you want to use, such as `deals.yourdomain.in`, and follow Cloudflare's DNS instructions.
4. If you want to use the root domain, such as `yourdomain.in`, follow the dashboard's specific instructions. The domain generally needs to be added to the same Cloudflare account as a zone.
5. Wait for DNS and TLS provisioning, then test HTTPS.

Do not overwrite existing DNS records until you understand what services currently use them. If the domain already serves another website, a subdomain is usually safer.

## Affiliate and privacy checklist

- Add your affiliate disclosure where visitors can easily see it.
- Follow each affiliate network's rules for link formatting, price displays, images, and disclosure.
- Keep prices and availability accurate; avoid fake urgency or unsupported discount claims.
- Publish a privacy policy appropriate to the analytics, cookies, and tracking you actually use.
- Add contact details and any required business disclosures before launch.
- Test every affiliate link and verify mobile layout.

## Important

This starter does not include live product feeds, automated price updates, checkout, user accounts, or a database. Product entries are manually maintained in `src/data/products.js`.
