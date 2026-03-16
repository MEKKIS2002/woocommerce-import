# WooCommerce CSV Import Agent

A Claude-powered web app that converts product catalogues and pricelists into WooCommerce-ready CSV files.

## Features

- Upload PDF, Excel, or CSV product catalogues
- Automatically generates WooCommerce import CSV with correct structure
- Handles variable products with variants (parent + variation)
- Generates SEO descriptions (English, 120–158 chars) and Norwegian product descriptions
- Finds HS/EU tariff codes automatically
- Unique SKU generation
- All defaults pre-set (stock, backorders, visibility, etc.)
- Commands: `/preview`, `/validate`, `/fill-prices`, `/fill-dimensions`, `/export`, `/search-tariff`
- Download CSV directly from the chat

## Hosting on GitHub Pages

1. Fork or clone this repo
2. Make sure `index.html` is in the root of the repository
3. Go to **Settings → Pages**
4. Under **Source**, select `Deploy from a branch`
5. Choose `main` branch and `/ (root)`
6. Save — your site will be live at `https://yourusername.github.io/your-repo-name`

## Usage

1. Open the app in your browser
2. (Optional) Upload a product catalogue using the file panel on the left
3. Describe your products or paste a URL, then chat with the agent
4. Use `/export` to generate the final CSV
5. Click the **Last ned CSV** button to download

## CSV Structure

The generated CSV follows the WooCommerce import format with these columns:

```
Id; Type; SKU; Parent; Name; Regular price; Tags; Short description for SEO;
Product Description (Norsk); In stock?; Stock; Backorders allowed?;
Weight (kg); Length (cm); Width (cm); Height (cm);
Meta: _logistra_robots_product_freight_description;
Meta: _logistra_robots_product_commodity_code;
Meta: _estimated_shipping_text;
Meta: _logistra_robots_product_country_of_origin;
Meta: _production_type;
Attribute 1 name; Attribute 1 value(s); Attribute 1 visible; Attribute 1 global;
Attribute 2 name; Attribute 2 value(s); Attribute 2 visible; Attribute 2 global;
Meta: _wpcom_is_markdown; Published; Is featured?; Visibility in catalog;
Allow customer reviews?
```

Delimiter: `;`

## Notes

- This app uses the Anthropic Claude API via the claude.ai interface
- It must be opened through claude.ai or the Claude app for the API calls to work
- No API key needed — authentication is handled by claude.ai

## License

MIT
