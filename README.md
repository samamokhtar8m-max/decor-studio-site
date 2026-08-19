# Decor Studio

A website showcasing and selling AI-generated interior designs (apartments, villas, rooms, gaming setups) and logos, with an order and reviews system connected to Supabase.

**Live link:** https://decor-studio-site-13d6a.web.app/

---

## Features

- Design gallery with filters (Villas / Full Apartments / Single Rooms / Gaming & Logos)
- Detail card with a center-opening animation when you click any design
- "Pick Your Color" section explaining the workflow (idea -> initial design -> execution)
- Materials section with a fanned-card effect
- Scroll reveal -- sections fade/rise into view as you scroll
- Reviews section (empty until real approved customer reviews come in)
- Supabase integration ready to go (database + Row Level Security)
- Fully responsive design (mobile / tablet / desktop), RTL Arabic layout

---

## Tech Stack

- **Frontend:** HTML / CSS / Vanilla JS (no framework)
- **Backend / Database:** Supabase -- Postgres + Auth + Storage + Row Level Security
- **Hosting:** Firebase Hosting
- **Fonts:** Markazi Text (serif) + Cairo (Arabic) from Google Fonts

---

## Project Structure

site/
- index.html              (main page)
- assets/
  - style.css              (all styling)
  - main.js                (filters + modal + scroll reveal)
  - supabase-client.js     (database connection, needs your keys)
  - img/                   (all design images)
- database/
  - schema.sql             (Supabase database schema)
- README.md

---

## Running Locally

The project is fully static, no build step needed. Just open index.html in any browser, or run a simple server:

cd site
python3 -m http.server 8000
# open http://localhost:8000

---

## Connecting Supabase (if not set up yet)

1. Create a free project at supabase.com
2. Go to SQL Editor and run the full database/schema.sql file
3. From Project Settings -> API, get:
   - Project URL
   - anon public key
4. Open assets/supabase-client.js and replace these placeholders:
   const SUPABASE_URL = 'your-project-url-here';
   const SUPABASE_ANON_KEY = 'your-anon-public-key-here';
5. Add this line in the head of index.html, before the supabase-client.js script tag:
   <script src="https://cdn.jsdelivr.net/npm/@supabase/supabase-js@2"></script>

Until these steps are done, the site runs fine on the static data already in index.html.

### Tables

| Table | Purpose |
|---|---|
| categories | Design categories |
| designs | The designs themselves (title, description, approximate price) |
| design_images | Images for each design |
| orders | Customer orders (custom order or request for an existing design) |
| reviews | Customer reviews (must be approved via is_approved before showing on the site) |

All tables are protected with Row Level Security: visitors can only read, writes (orders and reviews) are open for submission, and editing/deleting is admin-only via the Supabase Dashboard.

---

## Deploying to Firebase Hosting

npm install -g firebase-tools
firebase login
firebase init hosting   (public directory = . )
firebase deploy

---

## Contact

WhatsApp: 01014810906 (https://wa.me/201014810906)
