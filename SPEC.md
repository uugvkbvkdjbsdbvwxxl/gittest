# Static Mall SPA - Specification Document

## 1. Project Overview

- **Project Name**: ShopFlow - Static Mall SPA
- **Type**: Single Page Application (SPA) Static Website
- **Core Functionality**: A mock e-commerce platform with product browsing, details viewing, and shopping cart management
- **Target Users**: Online shoppers browsing products

## 2. UI/UX Specification

### Layout Structure

**Header (Fixed)**
- Logo on left
- Navigation links: Home, Cart (with badge count)
- Height: 64px
- Background: #ffffff with subtle shadow

**Main Content Area**
- Full viewport height minus header
- Three views: Home, Product Detail, Cart
- View switching via display: none/block

**Footer**
- Copyright text
- Height: 48px
- Background: #1a1a2e

### Visual Design

**Color Palette**
- Primary: #2563eb (Royal Blue)
- Secondary: #1a1a2e (Dark Navy)
- Accent: #f59e0b (Amber/Orange)
- Background: #f8fafc (Light Gray)
- Card Background: #ffffff
- Text Primary: #1e293b
- Text Secondary: #64748b
- Success: #10b981
- Border: #e2e8f0

**Typography**
- Font Family: 'DM Sans', sans-serif (headings), 'IBM Plex Sans', sans-serif (body)
- Headings: 24px (h1), 20px (h2), 16px (h3)
- Body: 14px
- Small: 12px

**Spacing System**
- Base unit: 8px
- Padding small: 8px
- Padding medium: 16px
- Padding large: 24px
- Gap: 16px
- Border radius: 8px (cards), 4px (buttons)

**Visual Effects**
- Card shadow: 0 2px 8px rgba(0,0,0,0.08)
- Card hover: translateY(-4px), shadow increase
- Button transitions: 0.2s ease
- Page transitions: fade 0.3s

### Components

**Navigation Bar**
- Logo text: "ShopFlow" with accent color
- Nav items with hover underline effect
- Cart badge: circular, accent color, shows item count

**Hero Carousel (Home)**
- Full width, 360px height
- Auto-slide every 4 seconds
- Manual navigation dots
- 3 promotional slides with gradient overlays

**Category Filter**
- Horizontal scrollable pills
- Active state: filled primary color
- Categories: All, Electronics, Clothing, Home, Sports, Books

**Product Grid**
- CSS Grid: 4 columns (desktop), 3 (tablet), 2 (mobile)
- Product card: image, title, price, rating, add-to-cart button
- Hover: lift effect

**Product Card**
- Image: 200px height, object-fit: cover
- Title: 2 lines max, ellipsis
- Price: bold, primary color
- Rating: stars with count
- Add to cart button: full width

**Product Detail View**
- Two column layout: image (50%) | details (50%)
- Large image with thumbnail gallery
- Title, price, description
- Specifications: color/size selection buttons
- Quantity selector: - / input / +
- Add to Cart button: large, primary

**Cart View**
- Table-like list of items
- Product thumbnail, name, specs
- Quantity controls
- Item total price
- Remove button
- Summary section: subtotal, checkout button
- Empty cart state

## 3. Functionality Specification

### Mock Data
- 12 products with: id, name, price, image, category, rating, description, specs (color, size), stock
- Images from picsum.photos

### Core Features

**Home View**
- Display hero carousel with 3 slides
- Category filter buttons (click filters products)
- Product grid showing all/filtered products
- Click product card → navigate to detail view
- Quick add to cart button on cards

**Product Detail View**
- Show product large image
- Display name, price, description, rating
- Color selection (if applicable)
- Size selection (if applicable)
- Quantity selector (min 1, max stock)
- Add to Cart button → adds to cart, shows feedback
- Back button → return to home

**Cart View**
- List all cart items
- Increase/decrease quantity (min 1)
- Remove item button
- Calculate subtotal
- Checkout button (shows alert)

**Routing**
- Hash-based routing: #home, #product/{id}, #cart
- Browser back/forward support
- Direct link to product

### User Interactions
- Smooth transitions between views
- Toast notification on add to cart
- Loading states (optional)
- Responsive on all devices

### Data Handling
- Cart stored in localStorage
- Cart persists on refresh
- Product data is static/mock

### Edge Cases
- Empty cart display
- Product out of stock (disable add)
- Invalid quantity (clamp to valid range)
- Missing product (404 state)

## 4. Acceptance Criteria

1. ✓ Three distinct views render correctly
2. ✓ Carousel auto-advances and responds to dot navigation
3. ✓ Category filters work and update product grid
4. ✓ Clicking product shows detail view with correct data
5. ✓ Add to cart updates cart badge count
6. ✓ Cart shows all added items with correct quantities
7. ✓ Quantity +/- works with limits
8. ✓ Total price calculates correctly
9. ✓ Cart persists after page refresh
10. ✓ Responsive design works on mobile/tablet/desktop
11. ✓ All animations are smooth
12. ✓ No console errors
