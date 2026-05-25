# AI Development Rules for Studio PRA Website

## Tech Stack Overview

- **Core Framework**: HTML5, CSS3, JavaScript (ES6+)
- **Styling**: Vanilla CSS with Tailwind-like utility classes (manually implemented)
- **Maps**: Leaflet.js for interactive maps with OpenStreetMap tiles
- **Icons**: Flag Icon CSS for country flags
- **Fonts**: Google Fonts (Montserrat) loaded asynchronously
- **Performance**: Optimized asset loading with preconnect, preload, and lazy loading
- **Responsive Design**: Mobile-first approach with media queries
- **Accessibility**: Semantic HTML and ARIA attributes where needed
- **No Build System**: Plain HTML/CSS/JS without bundlers or transpilers
- **Third-Party Services**: Limited to CDN-hosted resources only

## Library Usage Rules

1. **UI Components**:
   - Use native HTML elements whenever possible
   - For complex UI elements, implement custom solutions with vanilla JS
   - Absolutely NO React/Vue/Angular - this is a pure static site

2. **Styling**:
   - Use the existing utility classes pattern (similar to Tailwind)
   - Add new utility classes only when absolutely necessary
   - Keep all CSS in the `<style>` tags within HTML files
   - No CSS preprocessors (SASS/LESS) or CSS-in-JS

3. **JavaScript**:
   - Vanilla JS only - no jQuery or other JS frameworks
   - For maps, use Leaflet.js (already included)
   - All JS must be deferred or async loaded
   - No TypeScript - plain JavaScript only

4. **Performance**:
   - All assets must be loaded with performance optimizations:
     - `preload` for critical resources
     - `preconnect` for third-party domains
     - `loading="lazy"` for non-critical images
   - Minimize render-blocking resources
   - Keep bundle size under 150KB total (uncompressed)

5. **Third-Party Services**:
   - Only allowed services:
     - Google Fonts (for Montserrat)
     - OpenStreetMap (for map tiles)
     - UNPKG (for Leaflet)
     - Cloudflare CDN (for flag icons)
   - No Google Analytics or other tracking scripts
   - No social media widgets or embeds

6. **Accessibility**:
   - All interactive elements must be keyboard-navigable
   - Images must have proper alt text
   - Sufficient color contrast (WCAG AA minimum)
   - Semantic HTML structure (proper heading hierarchy)

7. **Browser Support**:
   - Latest 2 versions of Chrome, Firefox, Safari
   - IE11 is NOT supported
   - Progressive enhancement approach

8. **Code Organization**:
   - Keep all code in the HTML files (no external CSS/JS files)
   - Maintain consistent indentation (2 spaces)
   - Comment complex JavaScript logic
   - Group related CSS rules together with clear comments

9. **Security**:
   - All external resources must use HTTPS
   - No inline event handlers (use `addEventListener`)
   - Sanitize any dynamic content that could lead to XSS

10. **Maintenance**:
    - Document all additions/changes in the code
    - Keep the code as simple as possible
    - Avoid unnecessary abstractions