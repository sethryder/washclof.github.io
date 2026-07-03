# washclof.com

Personal hub page. Static files, no build step.

## Files

- `index.html` - home page (terminal style)
- `launcher.html` - alternate card layout, kept around but not linked from the home page
- `projects.json` - the project list, both pages read from it
- `support.js` - page runtime, required
- `CNAME` - custom domain for GitHub Pages

## Hosting on GitHub Pages

1. Create a repo and put these files in the root.
2. Repo Settings > Pages > "Deploy from a branch", pick `main` and `/ (root)`.
3. In the same Pages settings, set the custom domain to `washclof.com` (the CNAME file here covers it on the repo side).
4. At your DNS provider, point washclof.com at GitHub Pages: A records for the apex (185.199.108.153, .109., .110., .111.) and a CNAME record for `www` pointing to `<username>.github.io`.

## Adding a project

Add an entry to `projects.json`:

```json
{
  "name": "My New Tool",
  "url": "https://example.com",
  "domain": "example.com",
  "game": "EverQuest",
  "year": "2027",
  "color": "#2f6d8f",
  "desc": "One line about what it does."
}
```

`game` sets the tag color on the home page ("Minecraft" or "EverQuest"). `color` is only used as the card background on launcher.html. If you add a new game name it falls back to the EverQuest tag color.
