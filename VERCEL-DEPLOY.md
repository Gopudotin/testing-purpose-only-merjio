# Deploy to Vercel (free test) via GitHub

Use this to get a **test URL** (e.g. `something.vercel.app`) — not a Merjio-branded domain.

---

## 1. Push the project to GitHub

### 1.1 Initialize Git (if not already)

In a terminal, from the **project root** (`Merjio-website AI`):

```bash
cd "c:\Users\Lanware\Desktop\lanware\Merjio-website AI"
git init
git add .
git commit -m "Static Merjio site ready for Vercel test"
```

### 1.2 Create a repo on GitHub and push

1. Go to [github.com](https://github.com) and sign in.
2. Click **New repository**.
3. Name it something like `merjio-static-test` (or any name — it's for testing).
4. Choose **Public**, leave "Add a README" **unchecked** (you already have files).
5. Click **Create repository**.
6. On the new repo page, copy the **HTTPS** URL (e.g. `https://github.com/YOUR_USERNAME/merjio-static-test.git`).

Back in your terminal (still in project root):

```bash
git remote add origin https://github.com/YOUR_USERNAME/merjio-static-test.git
git branch -M main
git push -u origin main
```

Replace `YOUR_USERNAME/merjio-static-test` with your actual repo URL.

---

## 2. Deploy on Vercel (free)

1. Go to [vercel.com](https://vercel.com) and sign in (use **Continue with GitHub**).
2. Click **Add New…** → **Project**.
3. **Import** the repo you just pushed (e.g. `merjio-static-test`). Click **Import**.
4. **Important:** set the **Root Directory**:
   - Click **Edit** next to "Root Directory".
   - Enter: `web`
   - Confirm.  
   This makes Vercel use the `web` folder as the site root (where `index.html` and assets live).
5. Leave **Framework Preset** as **Other** (no build step).
6. Click **Deploy**.

Wait 1–2 minutes. Vercel will give you a URL like:

`https://merjio-static-test-xxxx.vercel.app`

That is your **free test URL** — not tied to Merjio’s real domain.

---

## 3. Check the deployed site

1. Open the URL Vercel showed (or go to the **Deployments** tab and click the link).
2. You should see the Merjio-style page at the root (thanks to `index.html`).
3. Click through: industries, SKIDs, scroll, etc.  
   - If any image or link still 404s, note the URL and we can fix it.

---

## Summary

| Step | What you do |
|------|-------------|
| 1 | `git init`, `git add .`, `git commit`, then create GitHub repo and `git remote add` + `git push` |
| 2 | Vercel → Add New → Project → Import your repo → set **Root Directory** to `web` → Deploy |
| 3 | Open the `*.vercel.app` URL and test the site |

Vercel’s free tier is enough for this static site. The test domain will be `*.vercel.app`, not merjio.com.
