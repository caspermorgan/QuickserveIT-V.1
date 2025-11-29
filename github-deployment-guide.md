# GitHub Deployment Guide for QuickServe IT Multi-Page Site

## 📁 Your Current Folder Structure

```
quickserve-it-agency/                    (Your repo folder)
├── index.html                           (Home page - existing)
├── style.css                            (Stylesheet - existing)
├── app.js                               (JavaScript - existing)
├── README.md                            (Optional)
└── services/                            (NEW FOLDER - create this)
    ├── index.html                       (NEW - services overview)
    ├── typing-document.html             (NEW - service detail 1)
    ├── school-institute.html            (NEW - service detail 2)
    ├── creator-services.html            (NEW - service detail 3)
    └── custom-work.html                 (NEW - service detail 4)
```

---

## ✅ Step 1: Verify Your GitHub Repo

**On your GitHub.com:**
1. Go to https://github.com/yourusername/quickserve-it-agency
2. You should see:
   - `index.html`
   - `app.js`
   - `style.css`
   - Any other files you have

If you don't see these, double-check your repo name.

---

## ✅ Step 2: Clone Your Repo (First Time Only)

**If you already have the repo locally, skip to Step 4.**

**If not, open Terminal/PowerShell and run:**

```bash
# Replace with your GitHub username
git clone https://github.com/yourusername/quickserve-it-agency.git

# Navigate into folder
cd quickserve-it-agency

# Check what files are there
ls -la
```

You should see `index.html`, `app.js`, `style.css`.

---

## ✅ Step 3: Create the `/services/` Folder

**In your project folder, create a new folder called `services`:**

**On Mac/Linux:**
```bash
mkdir services
```

**On Windows (PowerShell):**
```powershell
New-Item -ItemType Directory -Name services
```

**Or just create folder manually in your file explorer.**

---

## ✅ Step 4: Add the New HTML Files

**Copy and paste the following 5 files into the `services/` folder:**

1. **`services/index.html`** → Copy from file I created above
2. **`services/typing-document.html`** → Copy from file I created above
3. **`services/school-institute.html`** → (Need content - I can create)
4. **`services/creator-services.html`** → (Need content - I can create)
5. **`services/custom-work.html`** → (Need content - I can create)

---

## ✅ Step 5: Test Locally (Optional but Recommended)

**Before pushing to GitHub, test locally:**

```bash
# Navigate to your project
cd quickserve-it-agency

# Open index.html in your browser
# (Right-click → Open with → Browser)

# OR use Python to start a simple server
python3 -m http.server 8000

# Then visit http://localhost:8000 in your browser
```

**Test checklist:**
- ✓ Home page loads
- ✓ Click "Services" in nav → goes to `/services/index.html`
- ✓ Click on a service card → goes to detail page (e.g., `/services/typing-document.html`)
- ✓ Click "Back to Services" on detail page → goes back to services listing
- ✓ Breadcrumbs show correctly
- ✓ Language toggle works
- ✓ Theme toggle works

---

## ✅ Step 6: Push to GitHub

**Once tested, push the new files:**

```bash
# Navigate to project folder (if not already there)
cd quickserve-it-agency

# Check status (shows what files changed)
git status

# Add all new files
git add services/

# Commit with a message
git commit -m "Add multi-page service pages with breadcrumbs: typing, school, creator, custom"

# Push to GitHub
git push origin main

# Or if your branch is called 'master':
# git push origin master
```

**You should see output like:**
```
 5 files changed, 1200 insertions(+)
 create mode 100644 services/index.html
 create mode 100644 services/typing-document.html
 ...
```

---

## ✅ Step 7: Verify on Vercel

**Vercel auto-detects GitHub changes within 30 seconds:**

1. Go to https://vercel.com/dashboard
2. Click your "quickserve-it-agency" project
3. You should see a new deployment starting
4. Wait for green checkmark ✓ (usually takes 1-2 minutes)
5. Once deployed, visit:
   - https://quickserveit.vercel.app/
   - https://quickserveit.vercel.app/services/
   - https://quickserveit.vercel.app/services/typing-document.html
   - etc.

---

## ❌ Troubleshooting

### Issue: "Git is not recognized"
**Solution:** Install Git from https://git-scm.com/

### Issue: "fatal: Not a git repository"
**Solution:** Make sure you're in the correct folder:
```bash
pwd  # On Mac/Linux (shows current folder)
cd path/to/quickserve-it-agency  # Navigate to repo folder
```

### Issue: "Vercel is not deploying"
**Solution:**
1. Check GitHub repo → make sure files are there
2. Check Vercel dashboard → look for deployment errors
3. Check `.git/config` file → make sure repo URL is correct

### Issue: "Pages show 404 error"
**Solution:** 
1. Check file paths are correct (`services/index.html`, not `Services/Index.html`)
2. Make sure files actually got pushed: `git push` output should show files added
3. Wait 2-3 minutes and refresh Vercel dashboard

### Issue: "Links don't work"
**Solution:** Check that paths in HTML are correct:
- From home: `href="services/typing-document.html"`
- From service detail: `href="../index.html"` and `href="index.html"`

---

## 🚀 Complete Command Summary (Fastest Route)

```bash
# 1. Navigate to project
cd quickserve-it-agency

# 2. Create services folder
mkdir services

# 3. (Manually copy the 5 HTML files into services/ folder using text editor or file explorer)

# 4. Verify files are there
ls services/

# 5. Test locally (optional)
python3 -m http.server 8000
# Visit http://localhost:8000 in browser

# 6. Add and commit
git add services/
git commit -m "Add multi-page service pages"

# 7. Push to GitHub (auto-deploys to Vercel)
git push origin main

# 8. Done! Visit your site in 30 seconds
# https://quickserveit.vercel.app/services/
```

---

## 📋 What's Next?

After pushing these 5 pages:
1. Update your home page nav to link to `/services/`
2. Add other pages (About, Founder, Contact, Blog, FAQ, etc.)
3. Add a sitemap for SEO

---

## 🤔 Need Help?

**Common questions:**
- "Where do I add the files?" → In the `services/` folder on your computer
- "How do I know it worked?" → Visit https://quickserveit.vercel.app/services/
- "Can I test before pushing?" → Yes, use `python3 -m http.server` or open HTML in browser
- "What if I made a mistake?" → Use `git revert` to undo last commit

---

**Ready? Let me know when you want to:**
- Create the 3 remaining service pages (school, creator, custom)
- Or start updating your main `index.html` nav to link to the new services pages
- Or anything else!

