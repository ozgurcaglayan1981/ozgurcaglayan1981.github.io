# Personal Site

Plain HTML/CSS/JS — no build step, no backend, no database. $0 to host.

## Before you publish

1. Replace `assets/photo-placeholder.svg` with a real photo (`assets/photo.jpg`) and update the `src` in `index.html`.
2. Open `resume.html` in a browser, press Ctrl+P → "Save as PDF", and save the result as `assets/resume.pdf` (the "Download CV" button and the embedded PDF viewer in the About section both point here). `resume.html` already has your real experience/skills/certifications from LinkedIn — edit that file directly if anything needs updating, then re-export.
3. In `index.html`, the contact form posts to `https://formsubmit.co/caglayanozgur1981@gmail.com`. The **first submission** will trigger a confirmation email from FormSubmit — click it once to activate the endpoint, or the form won't deliver messages.
4. Everything in the Proof, Experience, and Case Studies sections is pulled from your LinkedIn and your two published Medium posts — edit freely if anything changes.

## Deploy for free — GitHub Pages

```bash
cd d:/projects/myapps/personal-site
git init
git add .
git commit -m "Initial personal site"
gh repo create personal-site --public --source=. --push
gh api repos/{owner}/personal-site/pages -X POST -f "source[branch]=main" -f "source[path]=/"
```

Then the site is live at `https://<your-github-username>.github.io/personal-site/`.

## Custom domain (optional, ~$10-15/year)

Buy a domain (Namecheap, Cloudflare Registrar, etc.), add a `CNAME` file to this folder with your domain name in it, and point the domain's DNS at GitHub Pages following [GitHub's custom domain docs](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site). GitHub issues a free SSL certificate automatically.
