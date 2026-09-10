# apps-privacy-policy

Public privacy policies for Idea2App applications, served by GitHub Pages.

**Live site:** https://idea-2-app.github.io/apps-privacy-policy/

## Layout

```
index.html              landing page — links every app policy
assets/style.css        shared styling (light + dark)
apps/<app-slug>/index.html   one folder per app
apps/template/          copy this to start a new policy
.nojekyll               serve files as-is, no Jekyll build
```

## Adding a new app

1. `cp -r apps/template apps/<app-slug>`
2. Edit `apps/<app-slug>/index.html` and replace every placeholder:
   `{{APP_NAME}}`, `{{LAST_UPDATED}}`, `{{IOS_BUNDLE_ID}}`, `{{ANDROID_PACKAGE}}`
3. **Delete the sections the app does not actually use** — the template marks the
   optional ones (location, camera/photos). A policy claiming permissions the app
   never requests is wrong, and one omitting permissions it does request will fail
   App Review.
4. Add a link in `index.html` between the `APPS:START` / `APPS:END` markers, and
   remove the "No application policies published yet" placeholder once the first
   one lands.
5. Commit and push to `main`. Pages redeploys automatically (about 1 minute).
6. Use `https://idea-2-app.github.io/apps-privacy-policy/apps/<app-slug>/` as the
   App Store and Google Play privacy policy URL.

## Rules

- Never delete or overwrite another app's policy folder.
- Never commit secrets — this repository is public.
