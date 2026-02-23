# Merjio website – run locally & deploy to your domain

## What you have in this folder

This is a **static export** of the Merjio site that was built on [Replit](https://product-showcase-dgbsganesh.replit.app/).  
It’s **not** the original Replit project (no source code, no `package.json`).  
It’s the built result: one HTML file plus JS/CSS and assets, so it can run anywhere you serve static files.

---

## Run it locally (after the fixes)

You **must** serve the `web` folder over HTTP (opening the HTML file directly often fails because of how the script is loaded).

**Option A – Node (recommended)**  
In a terminal, from the project root:

```bash
cd web
npx serve .
```

Then open the URL shown (e.g. `http://localhost:3000`) and open the Merjio HTML page from the file list.

**Option B – Python**

```bash
cd web
python -m http.server 8080
```

Then open:  
`http://localhost:8080/` and click the Merjio HTML file (or use its full URL).

---

## What was fixed for local run & future deployment

1. **Script path** – The HTML was loading `index-BzPSlZju.js.download`. Some environments don’t run that as JavaScript. It now loads `index-BzPSlZju.js` so the app runs correctly when served.
2. **Replit-only links** – The favicon and logo link pointed to `https://product-showcase-dgbsganesh.replit.app/...`. Those were changed to relative paths / `#` so the same files work locally and on your own domain (no dependency on Replit URLs).

If something still breaks locally (e.g. a specific image or link), the next step is to get the **actual Replit project** (the source code) from the person who built it, so you can fix and rebuild properly.

---

## Deploy to your own .com domain – two ways

### 1. Keep using Replit and add a custom domain (yes, you can)

- Replit **paid plans** support **custom domains**.
- So you can keep hosting the app on Replit and point **yourdomain.com** to it (no “replit” in the URL).
- The creator (or your team) would: in Replit, open the project → Deploy / Hosting settings → add your domain and follow Replit’s DNS instructions.

### 2. Deploy this static folder to any host (Vercel, Netlify, etc.)

- This `web` folder is static (HTML + JS + CSS + assets). You can deploy it to:
  - **Vercel** – drag-and-drop the `web` folder or connect a Git repo.
  - **Netlify** – same idea: upload `web` or connect repo, set publish directory to `web`.
  - **Any web host** – upload the contents of `web` to the public/html directory.
- After the fixes above, there are no hardcoded Replit URLs in the HTML, so it will work on your domain.

---

## What to do in code going forward

- **If you only have this zip (no Replit source):**  
  You can only edit the HTML/CSS and the minified JS (hard to maintain). Use it to run locally and deploy as static files. For real changes (new sections, logic, content), ask the original creator for the **Replit project** (or export from Replit so you get the full source and build setup).

- **If you get the Replit project:**  
  Clone or download it, run `npm install` and `npm run dev` (or the commands in its README), make fixes there, then either:
  - Keep deploying from Replit and add your custom domain there, or  
  - Run `npm run build`, take the built output (often a `dist` or `build` folder) and deploy that to Vercel/Netlify/your host the same way as this `web` folder.

---

## Optional: favicon on your domain

The zip doesn’t include a favicon file. To have one on your domain:

- Add a `favicon.png` (or `favicon.ico`) inside  
  `web/Merjio - Any Sensor. Any Industry. One Unified Data Layer _ Lanware IIoT_files/`  
  so the existing relative link in the HTML works, or  
- Edit the HTML and point the favicon `<link>` to your favicon path (e.g. `/favicon.png` at the root of your site).
