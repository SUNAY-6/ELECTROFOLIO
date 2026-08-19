# ECE Lab — Client (website)

Static React portfolio. **No Node server required** to run or deploy.

## Run on your computer

```bash
npm install
npm run dev
```

Open http://localhost:5173

Admin: http://localhost:5173/#/admin/login  
User `admin` / password `circuit2026`

## Build for hosting

```bash
npm install
npm run build
```

Upload the **`dist`** folder to any static host.

### GitHub Pages

1. Create a **public** GitHub repo and upload **this client folder only** (the files inside this zip).
2. If the repo is named `ece-portfolio`, build with:

```bash
# Windows PowerShell
$env:VITE_STATIC="true"
$env:VITE_BASE="/ece-portfolio/"
npm run build
```

```bash
# Mac / Linux
VITE_STATIC=true VITE_BASE=/ece-portfolio/ npm run build
```

3. Put the contents of `dist` on the `gh-pages` branch, **or** use the workflow in `.github/workflows/deploy-pages.yml` (copy that folder to the repo root).
4. GitHub → **Settings → Pages → Deploy from a branch → `gh-pages` / (root)**.

Do **not** point Pages at `main` — that only shows a README.

### Netlify / Cloudflare / Vercel (easier than Pages)

- Drag the `dist` folder onto [Netlify Drop](https://app.netlify.com/drop)
- Or connect the repo and set:
  - Base directory: `.` (this folder)
  - Build command: `npm run build`
  - Publish directory: `dist`

## Notes

- Admin data is stored in the browser (localStorage). Visitors do not share your edits.
- This zip is the website only. The API is a separate zip.
