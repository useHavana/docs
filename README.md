# Havana Public API Docs

Documentation for the Havana Public API — the CRM-agnostic, read-only API plus thin webhooks that lets customers write Havana engagement data (lead statuses, classified intents, transcripts, appointments, opt-outs) back into their own CRM.

This site is built with [Mintlify](https://mintlify.com) and deploys automatically from this repo.

## Structure

- `docs.json` — site config and navigation
- `index.mdx`, `authentication.mdx` — Getting Started
- `guides/` — daily CRM sync, webhooks, statuses and intents
- `api-reference/openapi.yaml` — the OpenAPI 3.1 spec; Mintlify auto-generates the API Reference pages (endpoints and webhook events) from it

The OpenAPI spec is authored in the backend repo at `api/public/v1/openapi.yaml`. When the spec changes there, copy the updated file to `api-reference/openapi.yaml` here.

## Local preview

Run from the repo root (where `docs.json` lives):

```bash
npx -y mint dev
```

Then open `http://localhost:3000`.

## Publishing

Changes merged to the default branch are deployed to production automatically via the Mintlify GitHub app.

## Troubleshooting

- If the dev server misbehaves, run `npx -y mint update` to get the latest CLI.
- If a page 404s locally, make sure you started `mint dev` in the folder containing `docs.json`.
