# arianify-website

The website at **arianify.com**, served with GitHub Pages. For now it holds only the privacy
policy of the Noot app for Android on Google Play (`com.arian.noot`).

Plain static HTML and CSS, with no build step, no JavaScript framework and no third-party
resources, so nothing on the page tracks visitors.

## Layout

| Path | What it is |
| --- | --- |
| `noot/privacy-policy/index.html` | Noot's privacy policy, at `https://arianify.com/noot/privacy-policy/`. Link this one in Google Play Console. |
| `index.html` | Redirects to the policy until the site has more pages. |
| `404.html` | GitHub Pages' not-found page. |
| `assets/` | Stylesheet and the Noot mark (also the favicon). |
| `CNAME` | The custom domain, `arianify.com`. GitHub Pages redirects `www.arianify.com` to it. |
| `.nojekyll` | Serve the files as they are, without Jekyll. |

## Publishing

1. Push to `main`.
2. In the repository: **Settings → Pages → Build and deployment**, choose **Deploy from a branch**, then `main` and `/ (root)`.
3. Point DNS at GitHub Pages:
   - `arianify.com` (apex): `A` records to `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - `www.arianify.com`: `CNAME` record to `<github-user>.github.io` (GitHub then redirects it to the apex)
4. Once the certificate is issued, tick **Enforce HTTPS** in the Pages settings.
5. In Play Console: **Policy and programs → App content → Privacy policy**, enter
   `https://arianify.com/noot/privacy-policy/`.

To preview locally, serve the folder with any static server, for example `npx serve .`, and open
`/noot/privacy-policy/`.

## Updating the policy

Edit `noot/privacy-policy/index.html` and change both dates in the header ("Effective date" only when the
terms change). Keep the policy in step with what the app and the server actually do. Google Play
checks it against the app's Data safety form.
