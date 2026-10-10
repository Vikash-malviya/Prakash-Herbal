# Prakash Herbal Website PRD

## Original problem statement
Create a responsive, luxury green/nature website for Prakash Herbal, a Rajasthan-based bulk seller, manufacturer, trader and exporter of herbs, spices, herbal teas, flowers, seeds, dehydrated products, dry fruits and superfoods. Include category-wise browsing, product selection, quantities and a WhatsApp enquiry form, alongside About, Products, Inquiry, Contact and Privacy sections. Use the supplied logo and business details.

## Architecture decisions
- Built the user-facing experience in the existing React frontend with responsive CSS and no sign-in or checkout requirement.
- Product catalogue is local/static for fast browsing and includes category filters and search.
- WhatsApp deep-link generation is handled in the browser using the supplied business WhatsApp number.
- Existing protected environment variables were not changed.

## Implemented
- Luxury earthy/organic visual system with supplied Prakash Herbal logo, responsive navigation and mobile menu.
- Hero section with Rajasthan positioning, MOQ information and trust signals.
- Searchable catalogue with Herbal Powders, Herbal Tea/TBC, Spices & Blends, Flowers & Seeds and Superfoods.
- Product cards with quick enquiry actions and a complete single-enquiry form.
- WhatsApp enquiry message includes product, category, quantity, unit, name, phone and delivery address.
- About/story, quality promise, contact actions, email, phone, address, GSTIN and privacy footer.

## Prioritized backlog
- P0: Confirm catalogue names and add any missing SKUs supplied by the business.
- P1: Add product images, downloadable catalogue and availability/pricing responses from the team.
- P2: Add enquiry history or CRM capture if the business later needs internal lead management.

## Next tasks
- Validate the exact final catalogue and product naming.
- Add business-approved product photography and packaging visuals.
- Connect enquiries to an internal lead dashboard if required.