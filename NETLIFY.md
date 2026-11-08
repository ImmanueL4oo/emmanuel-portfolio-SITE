# Netlify deployment handoff

Status: prepared locally; GitHub push and Netlify deployment are not confirmed. The existing private Work site has not been updated by this preparation.

## Verified project configuration

This V2 is plain HTML/CSS/JavaScript, not Next.js or React. There is no package.json, dependency installation, or compilation step. The deploy-ready files are tracked in dist/. netlify.toml sets publish = "dist" and an empty build command. Do not add npm run build, a Next.js plugin, or an SPA rewrite: navigation uses section anchors and native dialogs.

## GitHub to Netlify

1. Create or select the intended GitHub portfolio repository. Upload the CONTENTS of this portfolio-v2 folder at its root, including dist/, netlify.toml and this documentation. Do not upload the parent workspace or unrelated coursework. Keep dist tracked: it is the actual source and output.
2. In Netlify, add a project by importing an existing Git repository, choose GitHub, and authorize the selected repository.
3. Choose the actual production branch (main if that is the repository default). Leave base directory blank, build command blank, and publish directory dist. The root netlify.toml supplies the latter settings. If the entire portfolio-v2 folder is nested in a larger repository instead, set base directory to portfolio-v2.
4. Deploy, inspect the deploy log for success, then open the returned HTTPS URL in a signed-out/private browser. Do not report deployment as complete before those checks.
5. Check the portrait loads, mobile layout, keyboard navigation, all case-study dialogs, profile-summary download, motion pause/resume, and reduced-motion preference. Later pushes to the connected production branch should trigger new deployments.

## Private Work vs public Netlify

The existing Work site uses owner-only access. Its URL does not prove public availability. Netlify is a separate deployment: an unprotected published production site can be visited without ChatGPT access using its assigned netlify.app URL (or configured custom domain). Confirm actual access while signed out. GitHub repository visibility is separate from website visibility. No real Netlify URL is available yet.

## Portrait and accessibility

The original github-profile-800.jpg is copied unchanged into dist/; SHA-256 matches the uploaded attachment. No facial editing, regeneration, filters, or cropping were applied. The image has descriptive alt text, explicit dimensions, and responsive sizing. The dark palette, neural SVG, motion control, reduced-motion rules, keyboard focus styles, and native dialogs remain in place.

## Documentation

https://docs.netlify.com/manage/projects/add-new-project/
https://docs.netlify.com/build/configure-builds/overview/
