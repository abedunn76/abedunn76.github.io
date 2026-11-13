# Abe Dunn website: deploy and migration

Files in this folder
- index.html      the site (edit nothing; ask Claude to regenerate when publications change)
- robots.txt, sitemap.xml   for search engines (change www.abedunn.com to your domain)
- WEEBLY-REDIRECTS.txt      snippets for the old site
You add two files:
- cv.pdf     export your CV from Word (File > Save As > PDF), name it exactly cv.pdf
- photo.jpg  your headshot, square crop (the current one is on your Weebly site). If missing, the site shows your initials.

## 1. Domain (10 minutes, about $10-20/year)
Buy your name as a domain (e.g. abedunn.com; fallbacks: abedunn.org, abecdunn.com) at any registrar
(Cloudflare Registrar, Porkbun, Namecheap, Squarespace Domains). Turn on auto-renew.

## 2. GitHub Pages (15 minutes, free)
1. Create an account at github.com (a username you are happy to see in a URL, e.g. abedunn).
2. New repository named  <username>.github.io  , Public.
3. "Add file" > "Upload files": drag in index.html, cv.pdf, photo.jpg, robots.txt, sitemap.xml. Commit.
4. Settings > Pages > Source: "Deploy from a branch", branch main, folder / (root). Save.
   The site is live at https://<username>.github.io within a minute or two.

## 3. Connect the domain (15 minutes, then up to a day for DNS)
At your registrar's DNS page add:
- A records for @ (the bare domain): 185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153
- CNAME record: www  ->  <username>.github.io
In GitHub: Settings > Pages > Custom domain: www.abedunn.com > Save; then tick "Enforce HTTPS" once it is offered.
Optional: in index.html, just before </head>, add  <link rel="canonical" href="https://www.yourdomain.com/">

## 4. Move the traffic (20 minutes)
- Weebly: paste the snippets from WEEBLY-REDIRECTS.txt into each page's Header Code and publish.
- Google Search Console (search.google.com/search-console, sign in with your Google account):
  add your domain, verify via the DNS record it gives you, then submit sitemap.xml.
- Update every link that points at the old site:
  Google Scholar profile (Edit > Homepage), BEA researcher page (ask BEA web staff),
  your CV header link, email signature, LinkedIn, RePEc/IDEAS (if registered), conference and NBER bios.

## 5. Updating later
Edit index.html directly in GitHub (pencil icon) or ask Claude for a regenerated file and upload it over the old one.
To replace the CV, upload a new cv.pdf with the same name.
