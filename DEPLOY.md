# Deployment guide

This project is a Vue 2 application built with Vue CLI. The production-ready build output is in the `dist/` folder.

## Quick steps to deploy to Netlify (recommended)

1. In Netlify, click "New site" → "Import from Git" and connect your GitHub account.
2. Select the `Cconack/clemportfolio` repository.
3. Set the build command to:

```sh
npm run build
```

4. Set the publish directory to:

```
dist
```

5. Add any environment variables if needed, then Deploy site.

Alternative: Drag & drop the `dist/` folder to Netlify's "Sites" → "Create a new site" → "Deploy site" area.

## Push code to GitHub (if you want Netlify to auto-deploy)

You already have a remote at `https://github.com/Cconack/clemportfolio.git`.

Option A — Personal Access Token (PAT):
1. Create a PAT on GitHub with `repo` scope.
2. In terminal run:

```sh
git add .
git commit -m "Add deployment instructions"
# then
git push -u origin main
```

When prompted for a password, paste your PAT (not your GitHub password).

Option B — SSH (recommended long-term):
1. Generate an SSH key locally if you don't have one:

```sh
ssh-keygen -t ed25519 -C "your_email@example.com"
# or for older systems:
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

2. Copy the public key and add it to GitHub (Settings → SSH and GPG keys).
3. Change your remote to the SSH URL:

```shngit remote set-url origin git@github.com:Cconack/clemportfolio.git
```

4. Push normally:

```shngit push -u origin main
```

## Notes & suggestions
- The project built successfully, but the build warned about large image asset sizes — consider optimizing or compressing images in `src/assets` to improve performance.
- If you prefer CI/CD from GitHub, connecting the repo to Netlify will automatically build when you push to `main`.

If you want, I can (a) push for you if you paste a PAT now, or (b) switch the remote to SSH and help you set up an SSH key and add it to GitHub.
