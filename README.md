# COHORT website source code

Complete source for the standalone COHORT client demonstration delivered in this conversation.

## Files

- `index.html`: page shell; loads `styles.css` and `app.js`.
- `styles.css`: COHORT navy-and-blue theme, responsive layout and component styling.
- `app.js`: application state, views, workflows, browser persistence and exports.
- `test.cjs`: automated source/render-logic tests, when included.

## Run

Extract the ZIP and keep these files together. Open `index.html` in Chrome, Edge, Firefox or Safari.
No npm installation, build step, external library or internet connection is required.

If you prefer a local server and have Python installed:

```sh
cd COHORT_Source_Code
python -m http.server 8000
```

Then open http://localhost:8000 in your browser. Local hosting is optional.

## Test

With Node.js 20 or later installed:

```sh
node --check app.js
node test.cjs
```

The test script uses Node built-ins only. It checks source rendering and application logic with
minimal browser stubs, not real-browser interaction, security or payment-provider integrations.

## Edit

- Change colours and typography in the `:root` variables at the top of `styles.css`.
- Change sample workspaces, offerings, posts and packages in `seed()` in `app.js`.
- Change navigation in `navs`, and the views in functions such as `overview()`, `community()`
  and `offeringPage()`.
- Change workflow handling in `action()` and the individual save/purchase/refund functions.
- Open About this demo > Reset demo data after changing sample fixtures, otherwise previously
  saved browser state may continue to appear.

## Architecture and limitations

This version uses plain HTML, CSS and JavaScript, not Next.js or Supabase.
Browser localStorage stores demonstration state under `cohort-client-preview-v1` when supported.
Storage is local to the viewing browser and is not shared with other users. Browser settings,
private mode, file location and origin can affect persistence. A visible fallback appears if
storage is blocked.

All people, workspaces, lessons and financial activity are demonstration data.
No real login, email delivery, payments, refunds, recurring charges, secure file storage,
server-enforced tenant isolation or creator settlements are implemented.
Client-side access filtering is a visual workflow demonstration, not a security boundary.
Do not enter confidential data or secrets in this app.

The original planning document proposes a Next.js/PostgreSQL/Supabase production stack.
Implementing that backend, infrastructure and payment-provider integration is a separate
production-development step, not something included in this source package.
