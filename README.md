# Chaknith Bin — Apps

A small, static developer website for GitHub Pages. The website uses only HTML and CSS. Keep this repository separate from the Android app source and do not add signing files, credentials, or private configuration.

## Preview locally

Open `index.html` in a browser. For a local HTTP preview, run this from the repository root:

```sh
python -m http.server 8000
```

Then visit `http://localhost:8000/`. Stop the server with Ctrl+C.

## Edit the app listing

Edit `index.html` to change the app name and description. The Khmer Radio icon is copied from the Android project's launcher resources to `assets/khmer-radio-icon.webp`. When changing an icon, put the new image in `assets/` and update the image `src` and `alt` text in the app card.

The Khmer Radio card links to its Google Play listing. Update its `href` if the listing URL changes. The footer email link can be edited in `index.html` if your contact address changes.

To add another app, copy the `<article class="app-card">…</article>` block inside `.app-list`. Give its heading a unique `id`, update the article's `aria-labelledby` value, and replace all app-specific text and placeholders. Update the visible app count near the section heading. Styles are in `styles.css`.

## Publish with GitHub Pages

Create a **public**, separate GitHub repository named `YOUR_USERNAME.github.io`, replacing `YOUR_USERNAME` with your actual GitHub username. Put `index.html`, `styles.css`, `app-ads.txt`, this README, and the `assets/` folder at the repository root. Commit and push when you are ready to publish.

In the repository on GitHub, go to **Settings → Pages**. Under **Build and deployment**, select **Deploy from a branch**, then choose the **main** branch and **/(root)** folder. Save the setting. The website should become available at `https://YOUR_USERNAME.github.io/` after deployment. If you use a different repository name, its site URL includes that repository name, so it will not provide the requested root-level `app-ads.txt` URL.

## Add the website to Google Play

In Google Play Console, open each app's store listing and add the published developer website URL, `https://YOUR_USERNAME.github.io/`, in the website field. Replace the placeholder username with your actual username. Repeat for every app that uses this website for its app-ads.txt declaration, and save the listing changes.

## Check app-ads.txt

After GitHub Pages deploys, open `https://YOUR_USERNAME.github.io/app-ads.txt` in a browser, using your actual username. It should display this single line as plain text:

```text
google.com, pub-6488899443683538, DIRECT, f08c47fec0942fa0
```

If it does not load, confirm that `app-ads.txt` is at the repository root and Pages is publishing from **main** and **/(root)**. GitHub Pages deployment may take a few minutes.
