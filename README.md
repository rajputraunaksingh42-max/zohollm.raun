# Zoho LLM Dashboard

A React + TypeScript dashboard with an Express API, SQLite persistence, report management, spreadsheet uploads, and a local report-aware AI assistant.

## Features

- React + TypeScript + Vite frontend
- Express + SQLite backend
- Create, view, favorite, search, and delete reports
- CSV, XLS, and XLSX upload/parsing
- Dashboard KPIs and report/category views
- Local AI assistant based on stored report metadata
- Responsive UI
- Production build that can be served by the Express server
- GitHub Actions build check

## Requirements

- Node.js 18+ (Node.js 20 LTS recommended)
- npm 9+

## Run locally

```bash
npm install
npm run dev
```

Then open `http://localhost:5173`. The API runs on `http://localhost:4000`.

The Vite dev server proxies `/api` requests to the backend, so you normally do not need to configure an API URL locally.

## Production

Build the frontend and start the Express server:

```bash
npm install
npm run build
npm start
```

The production server uses `PORT` (default `4000`) and serves the built frontend from `dist/`.

For a separate frontend/backend deployment, set `VITE_API_URL` when building the frontend, for example:

```bash
VITE_API_URL=https://api.example.com/api npm run build
```

Backend CORS can be configured with `CLIENT_ORIGIN`. Copy `.env.example` to `.env` and adjust values as needed. **Never commit real secrets.**

## Data

SQLite is created automatically at `server/data/dashboard.db`. Database files and temporary uploads are ignored by Git.

## GitHub upload

```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin <YOUR_GITHUB_REPO_URL>
git push -u origin main
```

## Important

This repository is an MVP. For a real Zoho deployment, add authentication/authorization, Zoho OAuth and API scopes, a production LLM provider, audit logging, report permissions, background processing for large files, and any required PDF parsing. Keep all provider credentials on the server.
