# GistEngine Gist-the-main-point

Summarize any article by URL using RapidAPI’s Article Extractor & Summarizer. Built with React, Vite, Tailwind CSS, and Redux Toolkit Query.

## Quick start

- Node 18+ is recommended.

```bash
npm install
npm run dev
```

Open the local URL Vite prints (usually http://localhost:5173).

## Environment

Create a `.env` file at the project root:

```bash
# .env
VITE_RAPID_API_ARTICLE_KEY=your_rapidapi_key
```

The key is injected at build time and used in [src/services/article.js](src/services/article.js).

## Scripts

- `npm run dev` — start Vite dev server
- `npm run build` — production build
- `npm run preview` — preview the production build
- `npm run lint` — run ESLint

## Tech stack

- React 18 + Vite
- Tailwind CSS
- Redux Toolkit Query + React Redux
- PostCSS + Autoprefixer

## Project structure

```bash
.
├─ index.html
├─ package.json
├─ tailwind.config.js
├─ postcss.config.js
├─ vite.config.js
├─ src/
│  ├─ App.jsx
│  ├─ main.jsx
│  ├─ index.css
│  ├─ assets/
│  │  └─ index.js
│  ├─ components/
│  │  ├─ Hero.jsx
│  │  └─ Demo.jsx
│  └─ services/
│     ├─ article.js
│     └─ store.js
```

Key files:
- UI: [src/App.jsx](src/App.jsx), [src/components/Hero.jsx](src/components/Hero.jsx), [src/components/Demo.jsx](src/components/Demo.jsx), styles in [src/index.css](src/index.css)
- State/API:
  - Store: [src/services/store.js](src/services/store.js)
  - API slice: [src/services/article.js](src/services/article.js)
- App bootstrap: [src/main.jsx](src/main.jsx)
- Tailwind config: [tailwind.config.js](tailwind.config.js)

## How it works

- The API slice in [src/services/article.js](src/services/article.js) configures a base URL and RapidAPI headers, and exposes a `getSummary` query used by the UI.
- The Redux store is created in [src/services/store.js](src/services/store.js) and provided to the app in [src/main.jsx](src/main.jsx).
- The form in [src/components/Demo.jsx](src/components/Demo.jsx) sends the URL and renders the summary response.

## API details

- Base URL: https://article-extractor-and-summarizer.p.rapidapi.com/
- Endpoint used: `summarize?url={encodedUrl}&length=3`
- Required headers:
  - `X-RapidAPI-Key: <your key>`
  - `X-RapidAPI-Host: article-extractor-and-summarizer.p.rapidapi.com`

These are set in [src/services/article.js](src/services/article.js).

## Tailwind

Already configured with [tailwind.config.js](tailwind.config.js) and [postcss.config.js](postcss.config.js). Styles are imported in [src/App.jsx](src/App.jsx).

## Troubleshooting

- 401/403 from API: ensure `VITE_RAPID_API_ARTICLE_KEY` is set and valid.
- Vite env: restart dev server after changing `.env`.
- CORS/network failures: verify RapidAPI subscription and region.

## License

No license specified. Add one if you plan to distribute.
