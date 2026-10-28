# studioa.weeuradio.com, the fallback redirect

Only needed if connecting `studioa.weeuradio.com` to the site in
WordPress.com sends people to the home page instead of Studio A.

These files make a one-page site on GitHub Pages that sends anyone who
opens studioa.weeuradio.com to https://weeuradio.com/studioa/.

1. Create a public repository (Pages on a private one needs a paid plan),
   for example `jamestreese/studioa-redirect`, holding these four files.
   `404.html` is a copy of `index.html`, so any path redirects too.
2. Repository → Settings → Pages: deploy from the `main` branch, root.
   The `CNAME` file sets the custom domain.
3. In WordPress.com → Upgrades → Domains → weeuradio.com → DNS records,
   add a **CNAME** record: name `studioa`, value `jamestreese.github.io`.
   Remove the subdomain from the site's connected domains first, if it was
   added there.
4. Back in Settings → Pages, tick **Enforce HTTPS** once the certificate
   is issued (it can take up to an hour).

The page carries nothing private: Studio A itself still needs a WordPress
login. Here `robots.txt` blocks crawlers outright, since this host holds
nothing worth indexing; weeuradio.com/studioa/ says noindex instead.
