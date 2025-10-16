# 🚀 Deployment Tutorial: Deploy Your Website on Hostinger

This guide explains **how to deploy a website or web app (HTML, PHP, Node.js, or Next.js)** to **Hostinger** step by step.

---

## 🧩 1. Requirements

Before starting, make sure you have:
- ✅ A **Hostinger account**
- ✅ A **hosting plan** (Shared, VPS, or Cloud)
- ✅ A **domain name** (optional for testing)
- ✅ Your **project folder** ready for upload
- ✅ (Optional) Git installed on your local machine

---

## 🌐 2. Access Your Hosting Control Panel (hPanel)

1. Log in to [Hostinger](https://www.hostinger.com/).
2. Go to **hPanel → Websites** and choose your domain or hosting plan.
3. You’ll see the dashboard with tools like:
   - **File Manager**
   - **Databases**
   - **Git**
   - **Advanced → Terminal / SSH**

---

## 📦 3. Upload Your Project Files

### Option 1 — File Manager
1. Go to **Files → File Manager**.
2. Navigate to the folder `/public_html/`.
3. Click **Upload** and choose your project files (HTML, CSS, JS, etc.).
4. Make sure your **index.html** or **index.php** file is in `/public_html/`.

### Option 2 — FTP Client (Recommended for large projects)
1. In hPanel → **Files → FTP Accounts**, find your credentials.
2. Open **FileZilla** or any FTP client.
3. Connect using:
   - Host: your domain or IP  
   - Username: your FTP user  
   - Password: your FTP password  
   - Port: 21
4. Drag and drop your project files to `/public_html/`.

---

## 🧠 4. Deploy from GitHub (Optional)

1. In hPanel → **Advanced → Git**, click **Create a Repository**.
2. Choose:
   - Repository type: **Remote**
   - Repository URL: your GitHub repo URL (e.g., `https://github.com/username/project.git`)
   - Branch: `main`
3. Click **Create**.
4. Once created, you can **Pull Changes** anytime to update your site.

---

## ⚙️ 5. Configure Your Website

### For Static Sites (HTML, CSS, JS)
- Place files in `/public_html/`
- Default file: `index.html`
- You’re done! Visit your domain to see it live 🎉

### For PHP / Laravel Projects
1. Upload your PHP files into `/public_html/`.
2. If using Laravel:
   - Move all files except `public` outside `/public_html/`.
   - Move contents of `/public` into `/public_html/`.
   - Update paths in `index.php`.
3. Create a **database** in **Databases → MySQL Databases**.
4. Update `.env` with your new database credentials.

### For Node.js / Next.js Apps
> Shared hosting doesn’t support Node.js runtime.  
> You have two options:

1. **Use Hostinger VPS** for full Node.js support.
2. **Export Next.js app to static files**:
   ```bash
   npm run build
   npm run export
## 🔑 6. Set Up Environment Variables

1. Go to **Advanced → Environment Variables** (in hPanel).
2. Add your keys (like `DB_HOST`, `DB_USER`, `DB_PASS`, etc.).
3. Click **Save Changes**.

---

## 🧰 7. Test Your Website

Visit your domain, for example: `<https://yourdomain.com>`

If it’s not working, check:
- Files are in `/public_html/`
- DNS settings point to Hostinger
- There’s no missing `index.html` or `index.php` file

---

## 🔄 8. Updating Your Website

- **If using Git:** Go to hPanel → **Git → Pull Changes**
- **If using File Manager:** Replace files manually
- **If using FTP:** Upload and overwrite existing files

---

## 🧹 9. Optional: Enable HTTPS (SSL)

1. Go to **hPanel → SSL**
2. Click **Install SSL** for your domain
3. Wait for installation to complete
4. Your site will then be available at `<https://yourdomain.com>`

---

## 🧾 10. Summary

| Task | Tool | Path |
|------|------|------|
| Upload files | File Manager / FTP | `/public_html/` |
| Connect Git | hPanel → Git | Remote repo |
| Configure DB | hPanel → Databases | MySQL |
| Export Next.js | `npm run build && npm run export` | Upload `out/` |
| Secure site | hPanel → SSL | HTTPS |
