# Institution Branding Swap Guide

## Overview
This CSS template system allows you to quickly rebrand Canvas course templates for different institutions by simply updating the CSS variables at the top of the stylesheet. Follow these instructions to maintain WCAG color contrast compliance while customizing for your institution.

## Step-by-Step Instructions

### 1. Locate the Brand Variables Section
At the very top of your `style.css` file, find this section:

```css
/* ===================================================================
   BRAND VARIABLES (edit this block to swap branding for institutions)
   =================================================================== */
:root {
    --primary-color: #00274C;        /* UM Blue */
    --secondary-color: #FFCB05;      /* UM Maize */
    --accent-color: #0B57D0;         /* Accent Blue */
    --accent-light: #D7DEF7;         /* Light Accent */
    --accent-yellow-light: #FCF5CE;  /* Light Yellow */
    --accent-border: #305CDE;        /* Accent Border */

    --logo-main: url('...');
    --logo-wide: url('...');
    --icon-target: url('...');
    --icon-notebook: url('...');
    --icon-clock: url('...');
    --icon-lightbulb: url('...');
    --icon-list: url('...');
    
    --font-primary: "Atkinson Hyperlegible", Arial, sans-serif;
}
```

### 2. Update Color Variables

⚠️ **WCAG Compliance Warning**: When changing colors, maintain the light/dark relationships to ensure proper contrast ratios.

#### Primary Colors
- **`--primary-color`**: Main institution color (should be dark enough for white text)
  - Used for: headers, main accents, table headers
  - **Requirements**: Must have 4.5:1 contrast ratio with white text
  - **Example**: `#1B365D` (Penn State Blue)

- **`--secondary-color`**: Secondary institution color (often complementary)
  - Used for: borders, highlights, accent elements
  - **Requirements**: Should be visible on white backgrounds
  - **Example**: `#F68B1F` (Penn State Orange)

#### Accent Colors
- **`--accent-color`**: Interactive elements color
  - Used for: buttons, links, interactive headers
  - **Requirements**: Must contrast well with white text (4.5:1 ratio)
  - **Example**: `#0066CC` (Blue)

- **`--accent-border`**: Border accent color
  - Used for: decorative borders, table borders
  - **Requirements**: Should be darker than accent-light
  - **Example**: `#004488` (Darker blue)

#### Light Colors (Background Safe)
- **`--accent-light`**: Light background color
  - Used for: content blocks, table stripes, callout backgrounds
  - **Requirements**: Must be light enough for dark text (7:1 ratio preferred)
  - **Example**: `#E6F2FF` (Very light blue)

- **`--accent-yellow-light`**: Alternative light background
  - Used for: alternating content blocks, table stripes
  - **Requirements**: Must be light enough for dark text
  - **Example**: `#FFF8E1` (Very light yellow/cream)

### 3. Prepare Your Institution's Asset Folder

Create a folder with your institution's brand name containing all required assets:

#### Folder Structure
```
YOUR-INSTITUTION-NAME/
├── logo.png          (main/square logo)
├── wide-logo.png     (horizontal logo for footers)
├── target.png        (objectives icon)
├── notebook.png      (overview icon)
├── clock.png         (time/schedule icon)
├── lightbulb.png     (ideas/tips icon)
└── list.png          (resources/checklist icon)
```

#### Asset Requirements:
- **logo.png**: Square/compact format, 200x200px recommended
- **wide-logo.png**: Horizontal format, ~400x100px recommended  
- **Icons**: All icons should be 40x40px minimum, consistent style
- **Format**: PNG with transparent backgrounds preferred, SVG acceptable
- **Naming**: Must use exact filenames shown above (case-sensitive)

#### Folder Naming Convention:
- Use your institution's common abbreviation in ALL CAPS
- Examples: `UMICH`, `PSU`, `OSU`, `MSU`, `UCLA`, etc.
- No spaces, special characters, or lowercase letters

### 4. Update the Brand Folder Path

Once your folder is uploaded to the MO system, simply update the brand name in the CSS:

**Before (University of Michigan):**
```css
--logo-main: url('https://shared-files.online.umich.edu/mo-testing/UMICH/logo.png');
--logo-wide: url('https://shared-files.online.umich.edu/mo-testing/UMICH/wide-logo.png');
--icon-target: url('https://shared-files.online.umich.edu/mo-testing/UMICH/target.png');
--icon-notebook: url('https://shared-files.online.umich.edu/mo-testing/UMICH/notebook.png');
--icon-clock: url('https://shared-files.online.umich.edu/mo-testing/UMICH/clock.png');
--icon-lightbulb: url('https://shared-files.online.umich.edu/mo-testing/UMICH/lightbulb.png');
--icon-list: url('https://shared-files.online.umich.edu/mo-testing/UMICH/list.png');
```

**After (Penn State example):**
```css
--logo-main: url('https://shared-files.online.umich.edu/mo-testing/PSU/logo.png');
--logo-wide: url('https://shared-files.online.umich.edu/mo-testing/PSU/wide-logo.png');
--icon-target: url('https://shared-files.online.umich.edu/mo-testing/PSU/target.png');
--icon-notebook: url('https://shared-files.online.umich.edu/mo-testing/PSU/notebook.png');
--icon-clock: url('https://shared-files.online.umich.edu/mo-testing/PSU/clock.png');
--icon-lightbulb: url('https://shared-files.online.umich.edu/mo-testing/PSU/lightbulb.png');
--icon-list: url('https://shared-files.online.umich.edu/mo-testing/PSU/list.png');
```

**💡 Pro Tip**: You can use find-and-replace to change all instances of `/UMICH/` to `/YOUR-INSTITUTION/` in one step!

### 5. Update Font (Optional)

If your institution has a specific font requirement:

```css
--font-primary: "Your Institution Font", Arial, sans-serif;
```

Make sure the font is web-safe or properly loaded via Google Fonts or your CDN.

## Example Institution Rebrands

### Penn State Example
```css
:root {
    --primary-color: #1B365D;        /* Penn State Blue */
    --secondary-color: #F68B1F;      /* Penn State Orange */
    --accent-color: #0066CC;         
    --accent-light: #E6F2FF;         
    --accent-yellow-light: #FFF4E6;  
    --accent-border: #004488;        

    --logo-main: url('https://psu.edu/assets/logo-main.png');
    --logo-wide: url('https://psu.edu/assets/logo-wide.png');
    /* ... other icons ... */
}
```

### Ohio State Example
```css
:root {
    --primary-color: #BB0000;        /* OSU Scarlet */
    --secondary-color: #666666;      /* OSU Gray */
    --accent-color: #8B0000;         
    --accent-light: #FFE6E6;         
    --accent-yellow-light: #F5F5F5;  
    --accent-border: #660000;        

    --logo-main: url('https://osu.edu/assets/logo-main.png');
    --logo-wide: url('https://osu.edu/assets/logo-wide.png');
    /* ... other icons ... */
}
```

## Testing Your Changes

### 1. Visual Check
- Ensure all text is readable against backgrounds
- Verify logos display correctly at different sizes
- Check that colors align with your brand guidelines

### 2. Accessibility Check
Use tools like:
- **WebAIM Contrast Checker**: https://webaim.org/resources/contrastchecker/
- **Colour Contrast Analyser**: Free desktop tool
- **Browser DevTools**: Built-in accessibility audits

### 3. Required Contrast Ratios
- **Normal text**: 4.5:1 minimum
- **Large text** (18pt+ or 14pt+ bold): 3:1 minimum
- **Interactive elements**: 3:1 minimum for boundaries

## Common Issues and Solutions

### Issue: Text is hard to read
**Solution**: Adjust the lightness of background colors. Light backgrounds should be 85%+ lightness in HSL color space.

### Issue: Colors don't match brand exactly
**Solution**: Use your brand's approved web-safe color palette. Contact your institution's brand team for hex codes.

### Issue: Icons don't display
**Solution**: Verify URL paths are accessible and images are properly sized (40x40px minimum).

### Issue: Logos appear pixelated
**Solution**: Use high-resolution images (2x the display size) or SVG format for crisp display.

## Support

For technical support with implementation:
- Check that all URLs are accessible from Canvas
- Validate CSS using W3C CSS Validator
- Test across different devices and browsers

For brand compliance questions:
- Consult your institution's brand guidelines
- Verify color codes with your marketing/brand team
- Ensure proper logo usage and sizing

---

**Remember**: This system is designed for easy swapping - you should only need to modify the variables section at the top of the CSS file. The rest of the stylesheet will automatically adapt to your new branding!
