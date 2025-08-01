# Shopify Developer Assignment

## Project Overview
A fully functional, dynamic product page in Shopify that mirrors the provided Figma design. All product variations, pricing, and subscription details are pulled from the Shopify backend.

## Features Implemented

### 1. Product Media Gallery
- Product image carousel with thumbnail navigation
- Dynamic image updates based on selected variants
- Responsive design for all screen sizes

### 2. Purchase Options (Radio Group with Dynamic UI)
- Single Drink Subscription
- Double Drink Subscription
- Dynamic flavor selectors and pricing updates
- Real-time price calculations with 25% subscription discount + 20% sales discount

### 3. Flavor Selection
- Image swatches for Chocolate, Vanilla, Orange
- Single Drink: 1 flavor selector
- Double Drink: 2 selectors (Flavor 1 and Flavor 2)
- Required selection validation

### 4. Dynamic Pricing & Discounts
- Pulls pricing from Shopify backend
- Real-time price adjustments based on selections
- Displays both current and original prices
- Compare-at-price support for discounts

### 5. "What's Included" Box
- Dynamic content based on selected mode
- Delivery frequency and included items
- Bullet-point benefits per mode
- Managed via Shopify metafields

### 6. Add to Cart Logic
- Default selection: Single Drink Subscription with Chocolate
- AJAX cart updates
- Accurate variant reflection in cart

## File Structure
```
shopify-assignment/
├── assets/
│   ├── product-page.js
│   ├── product-page.css
│   └── images/
├── layout/
│   └── theme.liquid
├── sections/
│   └── product-page.liquid
├── snippets/
│   ├── product-gallery.liquid
│   ├── purchase-options.liquid
│   ├── flavor-selector.liquid
│   └── whats-included.liquid
├── templates/
│   └── product.liquid
└── config/
    └── settings_schema.json
```

## Setup Instructions
1. Upload theme files to Shopify development store
2. Create product with variants (Chocolate, Vanilla, Orange)
3. Set up metafields for "What's Included" content
4. Configure pricing rules in Shopify admin
5. Test all functionality

## Pricing Rules
- Subscription Price: 25% off from Main Price
- Sales Discount: 20% on all items
- Example: Main Price $100 → Subscription $75 → Final Price $80 (after 20% discount)

## Technologies Used
- Liquid (Shopify templating)
- JavaScript (ES6+)
- CSS/SCSS
- Shopify AJAX API
- Shopify Metafields #   S h o p i f y -  
 