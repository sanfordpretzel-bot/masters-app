# Masters leaderboard GitHub Pages app

This version is built for **GitHub Pages**, so it works on an iPad in Safari.

## What it does
- Shows a Masters leaderboard
- Lets you tap any player's name
- Opens a Wikipedia search for that golfer in a new tab
- Can auto-refresh `data.json` with a GitHub Action

## Easiest setup from an iPad
1. Install the **GitHub** app on your iPad, or use GitHub in Safari.
2. Create a new public repository, for example: `masters-leaderboard-app`.
3. Upload all files from this folder to the root of that repo.
4. In GitHub, go to **Settings → Pages**.
5. Under **Build and deployment**, choose **Deploy from a branch**.
6. Select your main branch and the **root /** folder.
7. Save.
8. Wait about a minute, then open the site URL GitHub gives you.

## Turn on auto-refresh
This repo includes `.github/workflows/update-leaderboard.yml`.

That workflow:
- runs every 30 minutes
- runs manually from the **Actions** tab
- updates `data.json`
- commits the refreshed file back to the repo

## Important note
The refresh script tries to parse the public ESPN Masters leaderboard page. If ESPN changes its page structure or blocks the request, the workflow keeps the last good `data.json` instead of breaking the site.

## Make it feel like an app on iPad
In Safari, open your GitHub Pages URL, tap **Share**, then tap **Add to Home Screen**.

## Files
- `index.html` - the site
- `data.json` - leaderboard data the page displays
- `scripts/update_data.py` - refresh script
- `.github/workflows/update-leaderboard.yml` - GitHub Action
