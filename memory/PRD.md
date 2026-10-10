# Prakash Herbal — PRD

## Original problem statement
Create a responsive B2B bulk-selling website for "Prakash Herbal" (herbs, spices, superfoods, etc.) with Amazon-like category selection. Must include a WhatsApp integration where users can select products, quantities, and provide contact details to open a pre-filled WhatsApp message. Needs About, Product, Inquiry, Contact, and Privacy sections. Theme should be luxury, organic, earthy (green/nature vibe). Includes specific contact details and a massive product catalogue ranging from 25KG to 10 tons.

## User personas
- Wholesale buyer / distributor comparing bulk botanical ingredients.
- Brand/formulation business sourcing herbs, spices, teas, flowers, seeds and superfoods.
- Business owner who wants fast WhatsApp enquiry with product, quantity and delivery details.

## Core requirements (static)
- Luxury organic earthy green theme.
- Responsive single-page site with Products, About, Inquiry, Contact and Privacy.
- Category selector for Herbal Powders, Herbal Tea/TBC, Spices & Blends, Flowers & Seeds, Superfoods.
- Large static catalogue with search and category filters.
- WhatsApp enquiry flow using +91 80059 87791.
- Visible business contact details: +91 81074 37791, Prakashherbalsojat@gmail.com, NH 162 Sardarpura, Sojat, Rajasthan 306104, GSTIN 08BCIPP4554K1Z3.

## Implemented
- July 2026: Initial React SPA catalogue, category filters, search, WhatsApp enquiry redirect, About/story, Contact and Privacy sections.
- July 2026: Text-first compact product cards, product detail side panel, Google Maps embed, white bold header, GST in top bar.
- July 2026: Replaced hero tree photo with herbal powder/spices image; updated all five collection category images; removed minimum-order line from top bar; locked/sticky header; rounded category cards; made WhatsApp number +91 80059 87791 visible in the top bar and Contact section; set the Contact map to coordinates 25.94225, 73.721528 (25°56'32.1"N 73°43'17.5"E).
- July 2026: Confirmed the frontend makes no API/database calls, cleaned the static HTML shell, set relative build paths (`homepage: "."`), generated the production build at `/app/frontend/build`, and verified the static build served over plain HTTP with category filters, images, mobile layout and WhatsApp enquiry URL generation.

## Architecture notes
- Frontend-only React SPA; product data is a static in-file catalogue in `frontend/src/App.js`.
- No backend API is used for enquiries; WhatsApp `wa.me` URL opens with a prefilled message.
- Styling is split between `App.css` and overrides in `index.css`.

## Prioritized backlog
- P0: Keep preview changes verified before any Deploy; live site updates only after user presses Deploy.
- P1: Add downloadable product spec sheet from the product detail panel.
- P1: Add a callback-request option for buyers who do not want to use WhatsApp.
- P2: Add certificates/quality proof section using the uploaded GST certificate.
- P2: Optional catalogue data cleanup by moving products into a dedicated data file without changing behavior.

## Next tasks
- Confirm the new imagery and visible WhatsApp number in preview.
- Deploy when the user approves the preview.
