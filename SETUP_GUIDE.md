# Shopify Theme Setup Guide

## Overview
This guide will help you set up the custom product page theme in your Shopify store.

## Prerequisites
- Shopify store with admin access
- Product with variants (Chocolate, Vanilla, Orange flavors)
- Metafields configured for "What's Included" content

## Step 1: Upload Theme Files

1. **Create a new theme in your Shopify admin:**
   - Go to Online Store > Themes
   - Click "Add theme" > "Upload theme"
   - Upload the theme files as a ZIP archive

2. **Theme file structure:**
   ```
   shopify-assignment/
   ├── assets/
   │   ├── product-page.js
   │   └── product-page.css
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

## Step 2: Configure Product

1. **Create a product with variants:**
   - Go to Products > Add product
   - Set product title and description
   - Add variants for each flavor:
     - Chocolate
     - Vanilla
     - Orange

2. **Set up product images:**
   - Upload product images for each variant
   - Ensure images are high quality and represent each flavor

3. **Configure pricing:**
   - Set base price for the product
   - The theme will automatically calculate:
     - 25% subscription discount
     - 20% sales discount
     - Final pricing based on selections

## Step 3: Configure Metafields (Optional)

1. **Create metafields for "What's Included" content:**
   - Go to Settings > Metafields
   - Create metafields for:
     - `custom.single_included` (HTML content)
     - `custom.double_included` (HTML content)
     - `custom.single_benefits` (HTML content)
     - `custom.double_benefits` (HTML content)

2. **Example metafield content:**
   ```html
   <!-- single_included -->
   <ul>
     <li>1 Premium Drink of your choice</li>
     <li>Monthly delivery to your door</li>
     <li>Flexible subscription management</li>
   </ul>
   
   <!-- single_benefits -->
   <ul>
     <li>25% subscription discount</li>
     <li>20% additional savings</li>
     <li>Cancel or pause anytime</li>
   </ul>
   ```

## Step 4: Add Flavor Swatch Images

1. **Upload flavor swatch images to assets:**
   - `chocolate-swatch.jpg`
   - `vanilla-swatch.jpg`
   - `orange-swatch.jpg`

2. **Image specifications:**
   - Size: 100x100px minimum
   - Format: JPG or PNG
   - Quality: High resolution
   - Content: Clear representation of each flavor

## Step 5: Test Functionality

1. **Test product page features:**
   - Gallery navigation
   - Subscription type selection
   - Flavor selection
   - Dynamic pricing
   - Add to cart functionality

2. **Verify pricing calculations:**
   - Base price: $100
   - Subscription discount (25%): $75
   - Sales discount (20%): $60
   - Final price: $60

3. **Test responsive design:**
   - Mobile devices
   - Tablet devices
   - Desktop browsers

## Step 6: Customize Theme Settings

1. **Access theme customizer:**
   - Go to Online Store > Themes
   - Click "Customize" on your active theme

2. **Configure settings:**
   - Colors (primary, secondary, success, error)
   - Typography (heading and body fonts)
   - Product page options
   - Cart settings

## Step 7: Launch

1. **Preview the theme:**
   - Use theme preview to test all functionality
   - Ensure all features work as expected

2. **Publish the theme:**
   - Click "Publish" to make it live
   - Test the live site thoroughly

## Troubleshooting

### Common Issues:

1. **Images not loading:**
   - Check file paths in flavor selector snippet
   - Ensure images are uploaded to assets folder

2. **Pricing not calculating correctly:**
   - Verify product variants are set up correctly
   - Check JavaScript console for errors

3. **Add to cart not working:**
   - Ensure product has valid variants
   - Check form submission in browser dev tools

4. **Metafields not displaying:**
   - Verify metafield namespace and key names
   - Check metafield content format

### Debug Mode:

Add this to your theme.liquid file for debugging:
```liquid
{% if request.design_mode %}
  <script>
    console.log('Product Data:', {{ product | json }});
    console.log('Metafields:', {{ product.metafields | json }});
  </script>
{% endif %}
```

## Support

For technical support or questions about the implementation, refer to:
- Shopify Theme Documentation
- Liquid Template Language Reference
- Shopify JavaScript API Documentation

## Performance Optimization

1. **Image optimization:**
   - Compress images before uploading
   - Use appropriate image formats
   - Implement lazy loading

2. **JavaScript optimization:**
   - Minify JavaScript files
   - Use async loading where appropriate
   - Optimize event listeners

3. **CSS optimization:**
   - Minify CSS files
   - Remove unused styles
   - Optimize selectors

## Security Considerations

1. **Input validation:**
   - Validate all form inputs
   - Sanitize user data
   - Implement CSRF protection

2. **Cart security:**
   - Use Shopify's built-in cart security
   - Validate variant selections
   - Implement proper error handling

## Maintenance

1. **Regular updates:**
   - Keep theme files updated
   - Monitor for Shopify platform changes
   - Update dependencies as needed

2. **Backup strategy:**
   - Regular theme backups
   - Version control for customizations
   - Document all custom changes 