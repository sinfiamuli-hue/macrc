# macrc.sinfia.net — Tea Room Beverage Report

Static single-file site (`index.html`) showing the Tea Room beverage
consumption & sales report, deployed as a subdomain of `sinfia.net`.

## Deploy on Cloudflare Pages

1. **Push this repo to GitHub**
   ```bash
   git remote add origin https://github.com/<your-username>/macrc-sinfia.git
   git branch -M main
   git push -u origin main
   ```

2. **Create a Cloudflare Pages project**
   - Cloudflare dashboard → **Workers & Pages** → **Create application** → **Pages** → **Connect to Git**
   - Select this repo
   - Build settings: leave **Build command** empty and **Build output directory** as `/`
     (it's a static file, nothing to build)
   - Deploy

3. **Attach the subdomain**
   - In the Pages project → **Custom domains** → **Set up a custom domain**
   - Enter `macrc.sinfia.net`
   - Cloudflare will auto-create the CNAME record if `sinfia.net` is already
     on your Cloudflare account (which it is, per existing sinfia.net setup)
   - Wait for the SSL certificate to activate (usually a couple of minutes)

4. Visit **https://macrc.sinfia.net** — done.

## Updating the data later

Replace `index.html` with a fresh export (or edit the `RAW_DATA` array near
the bottom of the `<script>` block directly), then:

```bash
git add index.html
git commit -m "Update beverage data"
git push
```

Cloudflare Pages redeploys automatically on every push to `main`.
