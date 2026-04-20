# The Dispute Desk

A gamified simulation built for the Mastering Dispute Management programme. Twenty timed decision scenarios, a career ladder from Junior Analyst to Chief Payments Officer, and a local browser-persistent leaderboard.

## Live URL

Once deployed, the simulation will be available at:

```
https://<your-github-username>.github.io/the-dispute-desk/
```

Replace `<your-github-username>` with your GitHub handle after you push.

## Deploy via GitHub Pages

Two paths. Pick whichever is easier.

### Path A. Browser only (no terminal)

1. Sign in to github.com.
2. Click the "+" icon in the top right and choose "New repository".
3. Repository name: `the-dispute-desk`. Visibility: Public. Check "Add a README". Click "Create repository".
4. In the new repo, click "Add file" > "Upload files". Drag `index.html` and `.nojekyll` into the upload area. Commit the upload.
5. Go to "Settings" > "Pages". Under "Build and deployment" set Source to "Deploy from a branch" and Branch to `main` / `/ (root)`. Save.
6. Wait about 60 seconds. The URL appears at the top of the Pages settings screen.

### Path B. Command line

From inside this folder:

```
git init
git add index.html .nojekyll README.md
git commit -m "Initial publish of The Dispute Desk simulation"
git branch -M main
git remote add origin https://github.com/<your-github-username>/the-dispute-desk.git
git push -u origin main
```

Then open the repo on github.com, go to Settings > Pages, and set Source to `main` / `/ (root)`. Save.

## Custom domain (optional)

If you own a domain, you can swap the URL to something like `disputedesk.intreensic.com`.

1. In the repo root, add a file called `CNAME` containing just the domain (one line, no protocol).
2. In your DNS provider, create a CNAME record pointing your subdomain to `<your-github-username>.github.io`.
3. Back in Settings > Pages, type the domain into "Custom domain" and tick "Enforce HTTPS".

Propagation typically takes 5 to 30 minutes.

## Updating the simulation

Any time you change `index.html` locally, push the change and GitHub Pages redeploys automatically within about a minute.

```
git add index.html
git commit -m "Update simulation content"
git push
```

## Technical notes

The simulation is a single self-contained HTML file. No build step, no dependencies. Everything (styles, JavaScript, questions, palettes, leaderboard) lives inline. The leaderboard writes to `localStorage` under key `dispute_desk_leaderboard_v1`.
