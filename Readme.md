# Moses Amartey — Portfolio

> Senior DevOps Engineer | AWS | Kubernetes | Terraform | CI/CD

Live portfolio website built with pure HTML/CSS/JS, deployed on Vercel via GitHub Actions.

---

## 🚀 Deploy in 5 Steps

### Step 1 — Create GitHub Repository

1. Go to [github.com](https://github.com) and click **New Repository**
2. Name it `moses-portfolio` (or any name you like)
3. Set it to **Public**
4. Click **Create repository**

### Step 2 — Push Files to GitHub

Open your terminal and run:

```bash
# Clone or initialize
git init
git add .
git commit -m "Initial portfolio deploy"
git branch -M main
git remote add origin https://github.com/yormengh/moses-portfolio.git
git push -u origin main
```

### Step 3 — Connect to Vercel

1. Go to [vercel.com](https://vercel.com) and sign in with GitHub
2. Click **Add New Project**
3. Select your `moses-portfolio` repository
4. Click **Deploy** — Vercel auto-detects static HTML

### Step 4 — Get Your Vercel Token & IDs (for GitHub Actions)

You need 3 secrets for the CI/CD pipeline:

#### VERCEL_TOKEN
1. Go to [vercel.com/account/tokens](https://vercel.com/account/tokens)
2. Click **Create Token** → name it `github-actions`
3. Copy the token

#### VERCEL_ORG_ID & VERCEL_PROJECT_ID
Run this in your terminal inside the project folder:
```bash
npm i -g vercel
vercel login
vercel link
```
Then check the `.vercel/project.json` file created — it contains:
```json
{
  "orgId": "YOUR_ORG_ID",
  "projectId": "YOUR_PROJECT_ID"
}
```

### Step 5 — Add Secrets to GitHub

1. Go to your GitHub repo → **Settings** → **Secrets and variables** → **Actions**
2. Click **New repository secret** and add all three:

| Secret Name | Value |
|---|---|
| `VERCEL_TOKEN` | Your Vercel token |
| `VERCEL_ORG_ID` | From `.vercel/project.json` |
| `VERCEL_PROJECT_ID` | From `.vercel/project.json` |

---

## ✅ How It Works After Setup

Every time you push to `main`:

```
git add .
git commit -m "Update portfolio"
git push
```

GitHub Actions automatically:
1. Installs Vercel CLI
2. Builds the project
3. Deploys to production on Vercel

You can watch it live under the **Actions** tab in your GitHub repo.

---

## 📁 Project Structure

```
moses-portfolio/
├── index.html                        # Main portfolio (single file)
├── vercel.json                       # Vercel deployment config
├── .github/
│   └── workflows/
│       └── deploy.yml                # GitHub Actions CI/CD pipeline
└── assets/
    ├── Moses-Amartey-Resume.pdf      # ← ADD YOUR RESUME HERE
    └── profile.jpg                   # ← Optional: external photo ref
```

---

## 📄 Adding Your Resume

1. Place your resume PDF inside the `assets/` folder
2. Name it exactly: `Moses-Amartey-Resume.pdf`
3. Push to GitHub — the download button in the portfolio links to it automatically

---

## 🌐 Custom Domain (Optional)

1. In Vercel dashboard → your project → **Settings** → **Domains**
2. Add your domain e.g. `mosesamartey.com`
3. Update your DNS records as instructed by Vercel

---

## 📬 Contact

- **Email:** yormengh@gmail.com
- **LinkedIn:** linkedin.com/in/moses-amartey
- **GitHub:** github.com/yormengh