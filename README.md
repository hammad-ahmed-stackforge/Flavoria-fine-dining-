# 🍽️ Flavoria Fine Dining — Restaurant Landing Page

A premium, fully responsive restaurant landing page built with **Tailwind CSS**, **FontAwesome**, and **vanilla JavaScript** — no frameworks, no build step, just a single self-contained HTML file ready to deploy anywhere.

Originally designed as an elegant international fine-dining concept, the menu has been localized for a **Pakistani restaurant in Hyderabad**, complete with PKR pricing and a working WhatsApp-based order form.

---

## ✨ Features

- **Sticky announcement bar** with click-to-call phone, click-to-email, and a live delivery-charge notice
- **Responsive navbar** with a smooth animated mobile hamburger menu
- **Split-layout hero section** with a rotating gold ring animation around the dish image, floating rating badge, and auto-cycling carousel dots
- **Horizontally scrollable menu categories** (Starters, Main Course, Desserts, Beverages, Pizza, Chef Specials)
- **Filterable "Chef's Recommendations" grid** — tabs (All / Starters / Main Course / Desserts / Beverages) instantly filter the dish cards with JavaScript, no page reload
- **8 Pakistani dishes** with real photography, star ratings, and PKR pricing:
  - Chicken Biryani — Rs. 650
  - Chicken Karahi — Rs. 1,200
  - Seekh Kebab — Rs. 750
  - Chicken Tikka — Rs. 550
  - Beef Nihari — Rs. 850
  - Gulab Jamun — Rs. 250
  - Shahi Tukda — Rs. 300
  - Mango Lassi — Rs. 200
- **Functional order form** with live order summary:
  - Customer name, phone, and delivery location (defaults to *Hyderabad*, fully editable)
  - Dish + quantity selector with auto-calculated subtotal, delivery charge, and total
  - "+" button on every dish card pre-selects that dish in the form and scrolls the page down to it
  - On submit, opens **WhatsApp** with a pre-filled order message sent directly to the restaurant's number — no backend or database required
- **Dark parallax-style special offer banner**
- **Feature highlights strip** (Fresh Ingredients, Expert Chefs, Cozy Ambiance, Fast Delivery)
- Scroll-triggered fade-up animations via `IntersectionObserver`
- Respects `prefers-reduced-motion` for accessibility
- Fully responsive — single column on mobile, multi-column grid on tablet/desktop

---

## 🛠️ Tech Stack

| Layer       | Technology                                  |
|-------------|----------------------------------------------|
| Styling     | [Tailwind CSS](https://tailwindcss.com) (via CDN) |
| Icons       | [Font Awesome 6](https://fontawesome.com)    |
| Fonts       | Google Fonts — *Playfair Display* (headings) & *Inter* (body) |
| Interactivity | Vanilla JavaScript (no frameworks)         |
| Images      | [Unsplash](https://unsplash.com) (free-license food photography) |

No `npm install`, no build tools, no dependencies to manage — just open the HTML file in a browser.

---

## 📂 Project Structure

```
flavoria-fine-dining/
└── index.html   ← everything (HTML + CSS + JS) lives in this one file
```

---

## 🚀 Getting Started

### Option 1 — Just open it
Download `index.html` and double-click it. It runs entirely in the browser since all dependencies load from CDNs.

### Option 2 — Run locally with a dev server
```bash
git clone https://github.com/<your-username>/flavoria-fine-dining.git
cd flavoria-fine-dining
python3 -m http.server 8080
```
Then visit `http://localhost:8080` in your browser.

### Option 3 — Deploy for free
Drag-and-drop the file into [Netlify Drop](https://app.netlify.com/drop), or push the repo and connect it to **GitHub Pages**, **Vercel**, or **Netlify** for a live URL in minutes.

---

## ⚙️ Customization Guide

All editable content lives directly inside `index.html` — search for these markers to update them quickly:

| What to change            | Where to look                                          |
|----------------------------|---------------------------------------------------------|
| Phone / email               | `TOP ANNOUNCEMENT BAR` section near the top            |
| Delivery charge              | Same top bar, plus the `DELIVERY_CHARGE` constant in the `<script>` |
| Dish names, prices, images   | `CHEF'S RECOMMENDATIONS` section — each dish is a `food-item` card |
| Order form dish list/prices  | `<select id="custDish">` inside the `PLACE YOUR ORDER` section — keep `data-price` in sync with the card prices above |
| WhatsApp number               | `RESTAURANT_WHATSAPP` constant in the `<script>` tag (international format, no `+` or spaces) |
| Default delivery location    | `value="Hyderabad"` on the `#custLocation` input        |
| Colors / fonts                 | `tailwind.config` block in the `<head>` (charcoal, cream, gold tokens) |

---

## 📱 How the Order Form Works

Since this is a static page with no backend or database, orders are routed through **WhatsApp** instead of a server:

1. Customer fills in their name, phone, delivery location, dish, and quantity.
2. The page calculates the subtotal + flat delivery charge live, in the browser.
3. On submit, JavaScript builds a formatted order summary and opens:
   ```
   https://wa.me/<restaurant-number>?text=<encoded-order-details>
   ```
4. WhatsApp opens (web or app) with the message pre-filled — the customer just hits send.

This is a common, practical pattern for small businesses that want real order intake without paying for hosting a backend.

---

## 🖼️ Image Credits

All food photography is sourced from [Unsplash](https://unsplash.com) under their free-to-use license. Swap any `images.unsplash.com` URL in the code with your own photography for a fully branded result.

---

## 📄 License

This project is free to use, modify, and deploy for personal or commercial restaurant projects.
