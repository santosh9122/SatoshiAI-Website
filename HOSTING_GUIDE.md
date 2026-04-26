# SatoshiAI Website — Complete Hosting Guide
## How to Deploy from GitHub to Netlify

This guide walks you through every step of hosting the SatoshiAI website using
GitHub for source code management and Netlify for live deployment.

---

## PART 1 — SET UP GITHUB

### Step 1: Create a GitHub Account (if you don't have one)

1. Go to https://github.com
2. Click **Sign up** in the top right corner
3. Enter your email address, create a password, and choose a username
4. Verify your email address when GitHub sends you a confirmation email
5. You now have a free GitHub account

---

### Step 2: Create a New Repository

1. After logging in, click the **+** icon in the top right corner
2. Select **New repository** from the dropdown menu
3. Fill in the details:
   - **Repository name:** `satoshiai-website` (or any name you prefer)
   - **Description:** `Official SatoshiAI Web3 Website`
   - **Visibility:** Set to **Public** (required for free Netlify hosting)
4. Leave all other options as they are
5. Click the green **Create repository** button

You will see a new empty repository page.

---

### Step 3: Upload Your Files to GitHub

You have two options. Use Option A if you are not comfortable with terminal commands.

#### Option A — Upload via the GitHub website (Easiest)

1. On your new empty repository page, click **uploading an existing file**
   (you will see this link in the middle of the page)
2. On the upload page, drag and drop ALL of the following files at once:
   - `index.html` (the main website file — renamed from satoshiai-final.html)
   - `admin.html`
   - `config.json`
   - `netlify.toml`
   - `satoshiai-whitepaper.pdf`
   - `satoshiai-logo.png`
   - `README.md`
3. Wait for all files to finish uploading (you will see green ticks appear)
4. Scroll down to the **Commit changes** section
5. In the first box, you can type a message like: `Initial commit — SatoshiAI website`
6. Click the green **Commit changes** button
7. All your files are now on GitHub

#### Option B — Upload via Terminal (Advanced)

If you have Git installed on your computer:

```bash
# 1. Open Terminal or Command Prompt
# 2. Navigate to the folder containing your files
cd /path/to/your/satoshiai-files

# 3. Initialise a git repository
git init

# 4. Add all files
git add .

# 5. Make the first commit
git commit -m "Initial commit — SatoshiAI website"

# 6. Connect to your GitHub repository
# Replace YOUR_USERNAME and YOUR_REPO_NAME with your actual values
git remote add origin https://github.com/YOUR_USERNAME/satoshiai-website.git

# 7. Push files to GitHub
git branch -M main
git push -u origin main
```

---

### Step 4: Verify Your Files Are on GitHub

1. Go back to your repository page: `https://github.com/YOUR_USERNAME/satoshiai-website`
2. You should see all 7 files listed in the repository
3. Click on any file to preview it and confirm it uploaded correctly
4. If you see all files, you are ready to connect to Netlify

---

## PART 2 — SET UP NETLIFY

### Step 5: Create a Netlify Account (if you don't have one)

1. Go to https://netlify.com
2. Click **Sign up** in the top right corner
3. Choose **Sign up with GitHub** — this is the easiest option as it links both accounts
4. Click **Authorize Netlify** when GitHub asks for permission
5. You now have a Netlify account connected to your GitHub

---

### Step 6: Deploy Your Site from GitHub

1. After logging in to Netlify, click **Add new site**
2. Select **Import an existing project**
3. Click **GitHub** under the "Connect to Git provider" section
4. If asked, click **Authorize Netlify** to give Netlify access to your repositories
5. You will see a list of your GitHub repositories
6. Click on **satoshiai-website** (or whatever you named your repository)

---

### Step 7: Configure Deployment Settings

1. Netlify will show you a configuration screen
2. Because your repository includes a `netlify.toml` file, Netlify will
   automatically detect all settings — you do not need to change anything
3. You will see:
   - **Branch to deploy:** main
   - **Build command:** (leave empty or it will show the echo command from netlify.toml)
   - **Publish directory:** .
4. Click the green **Deploy site** button

Netlify will now build and deploy your site. This usually takes 30 to 60 seconds.

---

### Step 8: View Your Live Site

1. After deployment, Netlify will show you a live URL that looks like:
   `https://random-name-123456.netlify.app`
2. Click the URL to open your live website
3. Check that everything works:
   - The homepage loads correctly
   - The logo appears
   - The Connect Wallet button opens the Phantom modal
   - Social links in the footer work
   - The Whitepaper download button works
   - The contract address copies when clicked
4. Your site is now live on the internet

---

### Step 9: Rename Your Site URL (Optional but Recommended)

The default Netlify URL uses a random name. You can change it to something cleaner:

1. In your Netlify dashboard, click on your site
2. Go to **Site configuration** (in the left sidebar)
3. Under **Site details**, click **Change site name**
4. Type your preferred name, for example: `satoshi-ai`
5. Click **Save**
6. Your new URL will be: `https://satoshi-ai.netlify.app`

---

### Step 10: Test the Admin Panel

1. Open your browser and go to: `https://yoursite.netlify.app/admin.html`
2. Enter your credentials:
   - **Username:** admin
   - **Password:** SatoshiAI2026!
3. After logging in, change your password immediately:
   - Scroll to **Change Admin Password**
   - Enter and confirm your new password
   - Click Save
4. The admin panel is now secured with your personal password

---

## PART 3 — UPDATING YOUR SITE

### How to Update Files

Every time you need to update the website (change content, update config, etc.),
follow these steps:

#### Option A — Update via GitHub Website

1. Go to your repository on GitHub
2. Click on the file you want to update (e.g. `config.json`)
3. Click the **pencil icon** (Edit this file) in the top right of the file preview
4. Make your changes directly in the browser editor
5. Scroll down, add a commit message (e.g. "Update Discord link")
6. Click **Commit changes**
7. Netlify detects the change automatically and redeploys within 30 seconds

#### Option B — Update via Admin Panel

1. Log in to the admin panel at `/admin.html`
2. Make your changes (toggle banner, update links, add GA4 ID)
3. Click the **Download config.json** button
4. The file downloads to your computer
5. Go to your GitHub repository
6. Click on `config.json` in the file list
7. Click the pencil icon to edit
8. Delete all existing content and paste the new config content
9. Commit the changes
10. Netlify redeploys automatically

#### Option C — Update via Terminal

```bash
# Navigate to your local project folder
cd /path/to/satoshiai-website

# Make your changes to the files locally

# Stage the changed files
git add .

# Commit with a description
git commit -m "Update tokenomics section"

# Push to GitHub — Netlify deploys automatically
git push
```

---

## PART 4 — CONNECT A CUSTOM DOMAIN (Optional)

If you have purchased a custom domain (e.g. satoshiai.io), follow these steps:

### Step 1: Add Domain to Netlify

1. In your Netlify site dashboard, click **Domain management**
2. Click **Add a domain**
3. Type your domain name (e.g. `satoshiai.io`) and click **Verify**
4. Click **Add domain**
5. Netlify will show you DNS records to configure

### Step 2: Configure Your Domain's DNS

Go to where you purchased your domain (Namecheap, GoDaddy, etc.) and
update the DNS settings:

**Option A — Use Netlify DNS (Recommended)**
1. In Netlify domain management, click **Set up Netlify DNS**
2. Follow the steps — Netlify provides you with 4 nameserver addresses
3. Go to your domain registrar and replace the existing nameservers with
   the 4 Netlify nameservers
4. DNS changes take 24–48 hours to fully propagate worldwide

**Option B — Keep Your Existing DNS Provider**
Add these DNS records at your registrar:
- **Type:** A | **Host:** @ | **Value:** 75.2.60.5
- **Type:** CNAME | **Host:** www | **Value:** yoursite.netlify.app

### Step 3: Enable HTTPS (SSL Certificate)

1. Once your domain is connected, go to **Domain management** in Netlify
2. Scroll to **HTTPS** section
3. Click **Verify DNS configuration**
4. If DNS is set up correctly, click **Provision certificate**
5. Netlify automatically installs a free SSL certificate
6. Your site now loads as `https://satoshiai.io` with the padlock icon

---

## PART 5 — ACTIVATE GOOGLE ANALYTICS

### Step 1: Create a GA4 Property

1. Go to https://analytics.google.com
2. Sign in with your Google account
3. Click **Start measuring** or **Create account** if you don't have one
4. Follow the setup wizard:
   - Account name: `SatoshiAI`
   - Property name: `satoshi-ai.netlify.app`
   - Industry: Finance
   - Time zone: Your local timezone
5. Click **Create**
6. Select **Web** as the platform
7. Enter your site URL and click **Create stream**
8. You will see your **Measurement ID** — it looks like: `G-XXXXXXXXXX`
9. Copy this ID

### Step 2: Add GA4 ID to Your Site

1. Log in to the admin panel at `/admin.html`
2. Scroll to the **Google Analytics** section
3. Paste your Measurement ID in the input field
4. Click **Save Analytics**
5. Click **Download config.json**
6. Upload the new `config.json` to your GitHub repository
7. Netlify redeploys — analytics is now active

After 24 hours you will start seeing visitor data in your Google Analytics dashboard.

---

## PART 6 — LIVE CHART ACTIVATION (After DEX Listing)

When satAI is listed on Raydium or Orca, the live chart can be activated:

1. Obtain your liquidity pool address from the DEX
2. In the `index.html` file, find the chart section and replace the placeholder:

```html
<!-- Replace the chart-ph div with this: -->
<iframe
  src="https://dexscreener.com/solana/YOUR_POOL_ADDRESS?embed=1&theme=dark"
  width="100%"
  height="400"
  frameborder="0"
  allow="clipboard-write"
  style="border-radius:16px;">
</iframe>
```

3. Also update the Buy satAI button link to a direct swap:

```html
<!-- Find this in the HTML: -->
href="https://raydium.io/"

<!-- Replace with your direct swap link: -->
href="https://raydium.io/swap/?inputCurrency=sol&outputCurrency=BHSd65jRJz3hnzKtuwnmCWWah3qwNVKZ6bHg4wLmri7i"
```

4. Commit and push the changes to GitHub
5. Netlify redeploys automatically

---

## QUICK REFERENCE

| Task | Where to do it |
|------|---------------|
| Update social links | Admin panel → Social Links → Download config.json → Upload to GitHub |
| Enable announcement banner | Admin panel → Announcement Banner → Toggle on |
| Add Discord link | Admin panel → Social Links → Discord field |
| Add Google Analytics | Admin panel → Google Analytics → Paste GA4 ID |
| Update whitepaper | Replace `satoshiai-whitepaper.pdf` in GitHub with new file |
| Activate live chart | Edit `index.html` in GitHub — replace chart placeholder |
| Update buy button | Edit `index.html` in GitHub — update href to swap URL |
| Change admin password | Admin panel → Change Admin Password section |
| View site analytics | analytics.google.com after GA4 is set up |

---

## TROUBLESHOOTING

**Site shows a file list instead of the homepage**
- Check that `netlify.toml` is uploaded to your GitHub repository
- The redirect rule in this file ensures the homepage loads correctly

**Images or logo not showing**
- Make sure `satoshiai-logo.png` is in the same directory as `index.html` in GitHub
- File names are case-sensitive — ensure the filename matches exactly

**Wallet connect button not working**
- The Phantom browser extension must be installed
- On mobile, use the Phantom app's built-in browser to visit the site
- Check browser console for errors (F12 → Console tab)

**Config changes not showing after upload**
- Netlify may take up to 60 seconds to redeploy after a GitHub push
- Hard refresh your browser: Ctrl + Shift + R (Windows) or Cmd + Shift + R (Mac)
- Check the Netlify dashboard → Deploys to confirm the latest deploy succeeded

**Admin panel password forgotten**
- The password is stored in your browser's localStorage
- Open browser DevTools (F12) → Application → Local Storage → your site URL
- Delete the key `satoshi_admin_pass` to reset to the default: `SatoshiAI2026!`

---

*SatoshiAI Website — Hosting & Deployment Guide — April 2026*
