# GrowTrans Solutions – Website

A static website (HTML + CSS + JavaScript, no build tools) for GrowTrans Solutions, Coimbatore.
Hosting: **Netlify free plan** (also handles the enquiry forms and resume uploads).

## 1. What is in this folder

```
growtrans-website/
├── index.html          Home
├── about.html          About Us
├── services.html       Our Services
├── employers.html      For Employers (enquiry form)
├── job-seekers.html    For Job Seekers (resume form with upload)
├── recruiters.html     Freelance Recruiters (enquiry form)
├── contact.html        Contact Us (contact form)
├── thank-you.html      Shown if a form is sent without JavaScript
├── 404.html            "Page not found"
├── css/style.css       All styling (colours are at the top)
├── js/config.js        ★ YOUR email + LinkedIn go here
├── js/main.js          Menu, animations, form sending
├── assets/             logo.svg, favicon.svg, hero-network.svg
├── robots.txt, sitemap.xml   SEO files (edit after you have your URL)
└── netlify.toml        Hosting settings
```

## 2. Add your real contact details (do this first)

Open `js/config.js` in Notepad (or any editor) and fill in:

```js
email: "hr@yourcompany.com",
linkedin: "https://www.linkedin.com/company/your-page",
```

Until you do, the site shows "[Business email – to be added]" instead of fake links.
Once filled in, the footer, contact page and error messages show clickable links automatically.

## 3. Run it on your computer

Easiest: double-click `index.html` – it opens in your browser. (The forms will not send
from your computer; they only work once the site is on Netlify.)

Optional, closer to the real thing: install Python, open a terminal in this folder and run
`python -m http.server 8000`, then visit http://localhost:8000.

**Test on mobile:** in Chrome press F12, then the phone/tablet icon (Ctrl+Shift+M).
After publishing, open the live link on your own phone.

## 4. Publish for free (GitHub + Netlify)

### A. Create a GitHub account and upload the code
1. Go to https://github.com/signup and create a free account.
2. Click **+** (top right) → **New repository**. Name it `growtrans-website`, choose **Public** or **Private**, click **Create repository**.
3. On the new repository page click **uploading an existing file**.
4. Open this folder on your computer, select **everything inside it** (all files and the `css`, `js`, `assets` folders) and drag it into the browser window.
   Make sure `index.html` is at the top level, not inside another folder.
5. Click **Commit changes**.

### B. Connect Netlify
1. Go to https://app.netlify.com/signup and sign up using **Continue with GitHub**.
2. Click **Add new project → Import an existing project → GitHub**, authorise, and pick `growtrans-website`.
3. Leave the build command empty and set **Publish directory** to `.` (a single dot). Click **Deploy**.
4. After about a minute you get a public address like `https://something-random.netlify.app`.
5. Change it: **Project configuration → Domain management → Options → Edit project name** (e.g. `growtrans`). Your link becomes `https://growtrans.netlify.app`.

That link can be shared on LinkedIn and in emails.

### C. Update the website later
Edit a file, then on GitHub open the file → pencil icon → **Commit changes**
(or drag new files into the repository). Netlify republishes automatically in about a minute.

### D. Custom domain (optional, later)
Buying a domain is not required to launch. When you have one:
Netlify → **Domain management → Add a domain** and follow the DNS instructions from your domain seller.
Then update `sitemap.xml` and `robots.txt` with the new address.

## 5. Make the forms work (important)

All four forms (employer, candidate/resume, recruiter, contact) use **Netlify Forms**.
There is no code to write, but check these after the first deploy:

1. In Netlify open your project → **Forms**. You should see: `employer-enquiry`, `candidate-resume`, `recruiter-network`, `contact`. (If not, redeploy: **Deploys → Trigger deploy**.)
2. **Get an email for every submission:** Project configuration → **Notifications → Emails → Form submission notifications → Add notification → Email notification**, choose a form (repeat for each) and enter your business email.
3. **Test each form yourself** on the live site and confirm the submission appears in **Forms**.
4. **Resumes** are stored with the submission in **Forms** (download from there). Files are limited to 5 MB in the page; Netlify's request limit is about 8 MB.
5. **Spam:** a hidden honeypot field is already included. In Forms → Settings you can also turn on spam filtering.

**Free-plan limits – please verify.** Netlify has changed its plans. Older accounts have
100 form submissions and about 10 MB of uploads per month; newer credit-based accounts
may differ. Check your own limits at Netlify → Usage/Billing. Resumes use up upload space
quickly, so also keep the email fallback visible (it is shown on the Job Seekers page once your email is set).
If you outgrow the free limits, alternatives are Formspree or Web3Forms (note: file upload is
often a paid feature there) – this would need a small change in `js/main.js`.

## 6. SEO

Every page has its own title, description and keywords for IT recruitment, IT staffing,
lateral hiring, contract staffing, bulk recruitment and Coimbatore. No ranking or lead
guarantees are made. After publishing:
1. Replace `YOUR-SITE-ADDRESS` in `sitemap.xml` and add the Sitemap line in `robots.txt`.
2. Add the site at https://search.google.com/search-console and submit the sitemap.
3. Create a Google Business Profile and a LinkedIn company page and link to the website.

## 7. Launch checklist

- [ ] `js/config.js` has your real email (and LinkedIn URL)
- [ ] Site published; project renamed to a clean `.netlify.app` address
- [ ] Each of the 4 forms tested on the live site and visible in Netlify → Forms
- [ ] Email notifications set up for every form
- [ ] Resume upload tested with a real PDF
- [ ] Checked on a phone and a desktop browser; menu works
- [ ] Read every page once; confirm all text is accurate for your business
- [ ] Add a Privacy Policy page (recommended, since you collect personal data and resumes)
- [ ] `sitemap.xml` / `robots.txt` updated; submitted to Google Search Console
- [ ] Website link added to LinkedIn page and email signature
- [ ] Phone number added (optional) only if you want one shown

## 8. Honest notes
- The site contains no invented client names, history, statistics or testimonials. Add real ones later.
- The illustrations are original SVG graphics, so there are no image licences to worry about.
- Fonts use the visitor's system fonts (fast, no external requests).
